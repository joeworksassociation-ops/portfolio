# Meu processo de desenvolvimento assistido por IA

Utilizo **GPT/Codex** para transformar requisitos em soluções funcionais. A ferramenta me ajuda com geração e alteração de código, análises, depuração, testes e documentação. Eu defino o objetivo, avalio as entregas e decido o que deve ser corrigido ou aprimorado.

## Etapas do meu trabalho

1. **Entender o problema:** observo obstáculos no fluxo de trabalho e as necessidades de quem vai utilizar a solução.
2. **Definir requisitos:** descrevo funcionalidades, regras de negócio, limites e critérios de validação.
3. **Implementar com IA:** oriento o GPT/Codex, analiso o resultado e solicito ajustes quando necessário.
4. **Testar:** verifico o funcionamento em cenários previstos, incluindo fluxos de dados, recuperação por backup e comportamento da interface.
5. **Ouvir usuários:** reúno sugestões e identifico melhorias com base na experiência prática.
6. **Evoluir:** priorizo correções, melhorias de usabilidade, segurança e qualidade.

## Exemplo: Preventivo

Parti da dificuldade de acompanhar acordos de pagamento durante atendimentos simultâneos. Transformei essa necessidade em um produto com busca, alertas de vencimento, confirmação manual de pagamentos, indicadores e cópia rápida de identificadores para consultas autorizadas.

**Tecnologias identificadas na aplicação:** HTML5, CSS3, JavaScript, Web Crypto API e armazenamento local no navegador.

**Ferramentas de apoio registradas no projeto:** GPT/Codex, além de Python, Node.js e PowerShell em tarefas auxiliares de desenvolvimento e verificação. A documentação técnica distingue ferramentas de apoio das tecnologias utilizadas pela aplicação em execução.

## Exemplo de iteração real: interface de anotações

Na evolução do Preventivo, **rejeitei uma primeira proposta de etiquetas** porque não atendia à organização visual que eu buscava. Reorientei a implementação para bandeirinhas com ícones, depois para **leitura de anotações dentro do próprio cartão**, com acesso rápido à edição. Em uma revisão posterior, corrigi uma exceção do tema vermelho e padronizei o acabamento dos cartões sem modificar a estrutura dos dados.

Esse ciclo demonstra como combino instruções à IA, avaliação de interface, feedback e testes de regressão. [Documentei as quatro revisões e minhas decisões](../projetos/preventivo/EVOLUCAO-R1-R4.md).

## Qualidade e transparência

Meu objetivo não é apenas obter código gerado por IA, mas validar se a solução funciona para o problema proposto. Uma análise anterior para este portfólio registrou **14 verificações automatizadas isoladas**. Em revisões posteriores, a R3 registrou **23 testes de interface e cinco verificações criptográficas**; a R4 registrou **27 testes de interface com Playwright/Chromium e cinco verificações separadas com Node Web Crypto**, todos aprovados nos cenários reportados.

A bateria de interface das revisões R3/R4 usou simulações de armazenamento e criptografia; os testes de Web Crypto real foram executados separadamente. **A R4 é uma base consolidada de desenvolvimento, não uma implantação em produção comprovada.** Esses resultados não substituem auditoria externa de segurança, homologação em HTTPS ou medições operacionais.

Não apresento resultados financeiros ou ganhos de tempo que ainda não foram medidos. [Leia o escopo e os limites da validação](../projetos/preventivo/VALIDACAO-R4.md).