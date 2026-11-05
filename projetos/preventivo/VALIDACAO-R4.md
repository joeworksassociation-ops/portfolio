# Preventivo — validação técnica e critérios de qualidade da R4

**Data da revisão:** 5 de novembro de 2026  
**Estado:** R4 consolidada como **base oficial de desenvolvimento**; homologação no domínio HTTPS de produção **não registrada** nesta auditoria.

## Escopo da mudança

A R4 corrigiu uma regra de estilo que fazia os cartões assumirem a cor vermelha quando esse tema era selecionado, contrariando a intenção de manter todos os cartões com fundo azul e variar apenas o contexto visual.

A alteração da R4 ficou restrita ao **CSS**. O HTML, a lógica JavaScript, a configuração de cabeçalhos, o esquema dos dados e as funções do cofre permaneceram sem mudanças em relação à R3, conforme a comparação técnica registrada na entrega.

**Decisões de interface:**

- Manter preenchimento azul-base dos cartões (`#102e42`) em **cinco temas**: Original, Vermelho, Esmeralda, Violeta e Âmbar.
- Preservar no tema vermelho o fundo da página, os painéis, a navegação e os filtros que fazem parte da identidade do tema.
- Aplicar borda fina em degradê ciano/verde-água, com textura e reflexo discretos, sem dificultar a leitura do cartão.
- Usar destaque suave ao passar o cursor, sem trocar a cor de fundo.
- Respeitar a preferência de **movimento reduzido** (`prefers-reduced-motion`).
- Manter bandeirinhas, anotações inline, pagamentos e navegação acessíveis.

## Execução de testes registrada

| Grupo | Resultado reportado | Ambiente e alcance |
| --- | --- | --- |
| **Interface e regressão** | **27/27 aprovados** | Playwright/Chromium, dados fictícios, com armazenamento e cifra simulados para a bateria de interface. |
| **Criptografia** | **5/5 aprovados** | Node.js com Web Crypto real, em verificações separadas. |
| **HTTPS em produção** | **Não testado** | Não existe homologação do site publicado registrada nessa auditoria. |
| **Segurança externa ou testes de desempenho operacional** | **Não realizados** | Os testes locais não constituem auditoria independente nem garantia de ausência de falhas. |

Os 27 cenários da R4 dão continuidade aos 23 testes da R3 e incluem quatro verificações adicionais da revisão visual: identidade dos cartões nos temas, contraste do cartão no vermelho, realce de hover e permanência da leitura de anotações após alterar o tema.

### Critérios observados

**Interface e acessibilidade:** o preenchimento do cartão foi identificado como `rgb(16, 46, 66)` em todos os cinco temas; as características computadas da borda, textura e sombra permaneceram consistentes. As interações de anotação foram exercitadas após a mudança visual.

**Anotações:** nas verificações herdadas da R3, foram exercitados criação, seleção, troca de nota, edição por duplo clique e por teclado, fechamento sem exclusão e renderização do texto como texto seguro, sem interpretação de HTML inserido pelo usuário.

**Criptografia (bateria separada):** cifra e decifra com AES-GCM 256 bits e derivação de chave PBKDF2 com 600 mil iterações; dados de anotação ausentes do JSON legível; rejeição de senha incorreta; leitura de etiquetas legadas sem ícone; rejeição de identificador de ícone fora do catálogo permitido.

**Regressão funcional:** os registros dos testes preservam os fluxos preexistentes de pagamento manual, cadastro, cofre e backups. A R4 não introduziu uma nova lógica de pagamentos nem uma conexão automática com sistemas financeiros.

## Limitações e evidências

- O conjunto de interface utiliza **simulação de armazenamento e criptografia**. Por isso, não apresento os 27 testes como 27 verificações de criptografia real.
- As cinco verificações de Web Crypto são reais, mas específicas e isoladas; não representam teste completo de segurança da aplicação.
- Não houve, no escopo dessa auditoria, medição do comportamento em computadores do ambiente operacional, validação em HTTPS de produção ou testes independentes de penetração.
- Os testes não comprovam aumento de produtividade nem adoção da R4 por todos os profissionais que já utilizam outras versões do Preventivo.
- O material de auditoria original foi mantido **fora deste repositório público**. Os scripts e os pacotes de aplicação não são publicados por decisão de preservação do código e da privacidade.

## Proteção da base e continuidade

A R4 foi aprovada como **base de desenvolvimento consolidada e protegida** em 5 de novembro de 2026. As revisões anteriores foram preservadas separadamente para rastreabilidade. Qualquer nova mudança deve partir de uma cópia, receber nova identificação e registrar alterações, resultados de teste e limitações.

Antes de substituir uma versão em uso, os cuidados registrados incluem exportar backup criptografado, verificar importação e reversão com dados fictícios e homologar os fluxos no domínio HTTPS autorizado. **Esse procedimento ainda não está registrado como concluído para a R4.**

---

[Estudo de caso da evolução R1–R4](EVOLUCAO-R1-R4.md) · [Voltar ao Preventivo](README.md)
