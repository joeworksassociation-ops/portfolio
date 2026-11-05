# Preventivo — estudo de caso

**Aplicação web de acompanhamento de negociações | Desenvolvimento assistido por GPT/Codex**

## Como surgiu

Identifiquei, no meu trabalho com atendimento de cobrança, uma dificuldade recorrente: após registrar promessas ou acordos, era necessário voltar a consultar os pagamentos, mesmo enquanto outros clientes continuavam sendo atendidos.

As anotações e planilhas não ofereciam uma experiência ágil e padronizada. Por isso, idealizei o **Preventivo** como ferramenta complementar para organizar registros e facilitar consultas durante o atendimento.

## O que desenvolvi

Com apoio do **GPT/Codex**, construí uma aplicação web com:

- Cadastro e pesquisa de registros por nome ou identificador.
- Acompanhamento de acordos, promessas e vencimentos.
- Destaque para compromissos próximos do vencimento ou atrasados.
- Ação de cópia rápida de identificadores para consultas autorizadas no sistema de origem.
- Atualização **manual** da situação do pagamento, após a verificação no sistema apropriado.
- **Dashboard dinâmico** com indicador circular de efetividade, contadores de pagamentos, gráficos por tipo de negociação e radar de vencimentos.
- **Filtros de pesquisa** por tipo e situação, com atualização automática dos indicadores conforme os registros são alterados.
- **Conquistas e feedback visual** ao confirmar novos resultados.
- Cofre local criptografado, com exportação e importação de backups protegidos por senha.

Os percentuais e gráficos são calculados automaticamente com base no estado dos negócios cadastrados, mas **a confirmação de pagamento continua manual** após consulta autorizada. A aplicação **não acessa diretamente os pagamentos do sistema de origem** e não utiliza IA para classificar clientes ou prever inadimplência. Utilizei IA **para desenvolver e aprimorar o software**.

[Conheça as telas, os indicadores e os fluxos do Preventivo](TELAS-E-FLUXOS.md).

## Evolução recente — R1 a R4 (novembro de 2026)

A experiência com o Preventivo me levou a redesenhar os cartões para consultar **anotações específicas por negócio** sem interromper o atendimento. O processo passou por quatro revisões: rejeitei etiquetas ovais que prejudicavam a leitura (**R1**), introduzi **bandeirinhas personalizáveis com nove ícones e seis cores** (**R2**), passei a apresentar a nota **diretamente na área central do cartão**, com edição por duplo clique ou botão (**R3**), e corrigi a aparência do **tema vermelho**, acrescentando bordas luminosas sutis com cartões azuis preservados nos cinco temas (**R4**).

Na R4, a correção foi limitada à camada de estilos: os dados, o cofre criptografado, a lógica de pagamento e os backups foram preservados conforme a documentação de auditoria. A versão foi **consolidada como base oficial de desenvolvimento em 05/11/2026**, mas **a sua implantação no site em produção não foi confirmada pelos testes disponíveis**. Não atribuo à R4, isoladamente, o uso já observado do produto por aproximadamente 15 colegas.

**Documentação desta evolução:** [estudo de caso e histórico R1–R4](EVOLUCAO-R1-R4.md) · [validação técnica R4](VALIDACAO-R4.md).

## Arquitetura

Na build analisada, foram identificados:

| Camada | Tecnologia |
| --- | --- |
| Interface | HTML5 e CSS3 |
| Lógica da aplicação | JavaScript |
| Armazenamento | localStorage do navegador |
| Proteção de registros | Web Crypto API, AES-GCM de 256 bits |
| Derivação de chave | PBKDF2-HMAC-SHA-256, 600 mil iterações |
| Backup | Arquivo JSON criptografado, recuperável com senha |

Optei por uma arquitetura **local-first**, sem login ou sincronização de registros em nuvem. O usuário precisa manter um backup criptografado para recuperar seus dados em outro computador ou depois da limpeza do armazenamento do navegador.

O armazenamento local e a criptografia são medidas de segurança, mas não substituem a avaliação dos procedimentos de proteção de dados no ambiente de utilização.

## Aplicação prática

Atualmente, aproximadamente **15 outros profissionais** utilizam e avaliam a ferramenta, contribuindo com testes e sugestões de melhorias. O projeto surgiu em uma operação de cobrança de produtos financeiros de **uma grande empresa brasileira do varejo de moda**.

O ganho observado está na organização das informações, na identificação de vencimentos e na redução de etapas manuais durante o atendimento. Ainda não medi formalmente a economia de tempo ou qualquer impacto financeiro, por isso não atribuo números a esses benefícios.

[Leia mais sobre o problema e a aplicação profissional](CONTEXTO-PROFISSIONAL.md).

## Testes e evolução

Testei as funcionalidades no uso prático e acompanhei o retorno de colegas. Uma análise anterior para este portfólio registrou **14 verificações automatizadas isoladas**, incluindo criptografia, recuperação por senha e validação de dados.

Em uma **bateria posterior e distinta**, a revisão R3 registrou **23/23 testes de interface e 5/5 testes criptográficos**; a R4 ampliou essa cobertura para **27/27 testes de interface com Playwright/Chromium e 5/5 verificações separadas com Node Web Crypto**. A bateria de interface usou **simulação de armazenamento e criptografia**, enquanto os cinco testes criptográficos executaram Web Crypto real de forma isolada.

Esses resultados não equivalem a uma auditoria externa de segurança nem comprovam que a R4 tenha sido homologada no domínio HTTPS de produção. Continuo reunindo feedback e preservando revisões para evolução e eventual reversão segura.

[Detalhes dos cenários, testes e limitações](VALIDACAO-R4.md).

## Apresentação pública

Neste portfólio, mostro o projeto e suas decisões técnicas **sem identificar a organização ou seus sistemas internos**. Não disponibilizo dados reais, backups dos usuários nem o código da aplicação utilizada no ambiente profissional. As capturas recebidas estão em revisão para anonimização; as versões com identificadores visíveis permanecem fora do repositório público. Somente imagens com conteúdo fictício ou integralmente anonimizado serão publicadas.