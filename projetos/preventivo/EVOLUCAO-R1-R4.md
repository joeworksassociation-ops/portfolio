# Preventivo — evolução da interface: etiquetas, anotações e temas

**Estudo de caso de desenvolvimento iterativo com GPT/Codex · 5 de novembro de 2026**

> **Situação das versões:** a R4 é minha **base oficial consolidada para desenvolvimento**, aprovada para servir de referência às próximas alterações. Os testes documentados foram realizados em ambiente local. A homologação da R4 no site em produção não consta nas evidências desta revisão; portanto, não apresento as funcionalidades novas como já implantadas para todos os usuários.

## O problema que quis resolver

Ao utilizar o Preventivo para acompanhar promessas e acordos de pagamento, identifiquei a necessidade de manter **anotações rápidas e específicas em cada negócio**. A informação precisava ficar fácil de localizar sem aumentar a quantidade de janelas abertas durante o atendimento.

Além de criar a funcionalidade, procurei manter os cartões legíveis, visualmente consistentes entre os diferentes temas e compatíveis com o cofre local criptografado.

## Da primeira proposta à versão consolidada

| Revisão | Decisão e implementação | Aprendizado / resultado |
| --- | --- | --- |
| **R1 — etiquetas coloridas** | Estruturei etiquetas com título, anotação e seis cores; a primeira interface exibia pílulas abaixo do CPF. | **Rejeitei a proposta visual:** a disposição criava ruído na área de leitura e não correspondia à hierarquia desejada. |
| **R2 — bandeirinhas com ícones** | Substituí as pílulas por bandeirinhas com recorte em V, seis cores e nove ícones personalizáveis. Separei o botão `+` das marcações e mantive o controle de pagamento independente. | A organização visual foi aprovada; as bandeirinhas passaram a representar atalhos para notas de cada negócio. |
| **R3 — leitura dentro do cartão** | Centralizei as bandeirinhas no cabeçalho e reservei o `+` para o canto direito. O clique simples passou a abrir a anotação **dentro do próprio cartão**, sem modal; a edição permaneceu acessível por duplo clique e por um botão explícito. | Reduzi a necessidade de abrir janelas apenas para consultar notas, sem modificar o formato dos registros. |
| **R4 — consistência entre temas** | Corrigi uma exceção de CSS que deixava cartões vermelhos no tema vermelho. Preservei os cartões em azul nos cinco temas e adicionei bordas luminosas discretas em ciano/verde-água, textura sutil e realce de hover. | Alcancei a identidade visual desejada em testes locais, com alteração restrita ao CSS e sem mudar dados ou criptografia. |

## Como funcionam as bandeirinhas na R4

- Cada negociação pode ter **até 12 anotações**, com título, texto, cor e ícone escolhidos pelo usuário.
- Há **seis cores** (`coral`, `amber`, `mint`, `sky`, `lilac`, `rose`) e **nove tipos de ícone**: nota, alfinete, marcador, estrela, telefone, calendário, alerta, concluído e relógio.
- **Clique simples:** seleciona a bandeirinha e mostra sua anotação na área central do negócio.
- **Duplo clique:** abre a edição. Também é possível editar por botão próprio no painel e por teclado.
- **Fechar:** recolhe o painel, sem apagar a anotação; trocar de bandeirinha mostra o texto correspondente.
- Depois de criar ou editar uma anotação, o painel exibe o item correspondente. Ao apagar a anotação selecionada, a área de leitura é recolhida.
- As notas ficam vinculadas ao respectivo negócio no cofre criptografado. A seleção visual aberta é transitória e não precisa ser salva no backup.
- A interface mantém recursos de acessibilidade e responsividade para uso com teclado, telas menores e dispositivos sensíveis ao toque.

**Compatibilidade:** o formato das anotações da R2 permaneceu compatível com R3 e R4. Etiquetas anteriores sem ícone recebem um ícone padrão. Os controles de pagamento, indicadores e backups permanecem independentes das bandeirinhas.

## Por que mantive os cartões azuis no tema vermelho

A mudança de tema deve personalizar o contexto da aplicação, não prejudicar a identificação e a leitura dos negócios. Na R3, uma regra específica aplicava vermelho também aos cartões e à lista, diferentemente dos demais temas.

Na R4, padronizei o preenchimento azul dos cartões, inclusive quando o fundo geral, os painéis e os filtros estão em vermelho. Acrescentei um contorno fino com degradê, reflexo e textura discretos sem transformar o cartão em um elemento excessivamente chamativo. O destaque de hover não altera o preenchimento do cartão, e o estilo respeita a preferência do sistema por movimento reduzido.

A alteração foi **exclusivamente visual**: nessa revisão, apenas a folha de estilos foi modificada; estrutura HTML, lógica JavaScript, configurações de cabeçalhos e esquema dos dados permaneceram preservados, conforme o registro técnico da entrega.

## Verificações da implementação

| Revisão | Interface | Criptografia | Alcance dos testes |
| --- | --- | --- | --- |
| **R3** | **23/23** cenários aprovados em Chromium | **5/5** verificações reais com Web Crypto | Interface testada com armazenamento e criptografia simulados; criptografia real testada separadamente. |
| **R4** | **27/27** cenários aprovados com Playwright/Chromium | **5/5** verificações reais com Node Web Crypto | Inclui verificação visual dos cinco temas, realce de hover, permanência do painel de notas e regressões anteriores. |

Os testes de interface utilizaram dados fictícios e simulações para armazenamento/cifra. As cinco verificações criptográficas reais foram executadas separadamente. **Não realizei, nessa revisão, homologação no domínio HTTPS de produção, medição de desempenho na operação ou auditoria externa de segurança.**

[Leia o relatório de validação e suas limitações](VALIDACAO-R4.md).

## Meu papel e o uso da IA

Identifiquei o problema, defini as regras de interação, avaliei as opções visuais e rejeitei a primeira proposta. Utilizei **GPT/Codex** como apoio para implementação, ajustes e investigação dos problemas; posteriormente, comparei o resultado com o comportamento esperado e solicitei correções até consolidar a base R4.

O processo mostra a importância da **validação humana do resultado gerado com IA**: uma primeira implementação funcional não precisa ser a solução de interface mais adequada.

## Resultado e próximos passos

Consolidei a **R4 como base oficial protegida para futuras evoluções**, sem sobrescrever as revisões anteriores. Para avaliar o impacto real das bandeirinhas entre os profissionais que usam o Preventivo, ainda são necessários homologação em ambiente apropriado e feedback específico sobre a revisão.

Não atribuo à R4 ganhos de produtividade ou tempo economizado sem medição. As aproximadamente 15 pessoas mencionadas no [estudo de caso principal](README.md) utilizam e avaliam o **Preventivo como produto**, e esse dado não comprova, por si só, a adoção da R4.

### Privacidade e distribuição

Esta documentação não disponibiliza código-fonte, ZIP de aplicação, conteúdo do cofre, CPF, nomes de clientes ou informações de sistemas internos. As evidências visuais destinadas ao público devem usar exclusivamente dados fictícios ou anonimização integral.

---

[Voltar ao Preventivo](README.md) · [Telas e fluxos](TELAS-E-FLUXOS.md) · [Validação técnica](VALIDACAO-R4.md)
