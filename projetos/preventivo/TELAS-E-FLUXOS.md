# Preventivo — telas, funcionalidades e experiência de uso

**Estudo de caso visual e funcional | Aplicação web desenvolvida com apoio de GPT/Codex**

Criei o Preventivo para acompanhar negociações em um fluxo de atendimento que exige consultas rápidas, organização de prazos e visualização de resultados. As telas documentadas abaixo mostram como transformei essa necessidade em uma aplicação web utilizável no dia a dia.

> **Sobre as imagens:** selecionei dez capturas da interface e preparei versões editadas, com partes dos nomes desfocadas e ocultação do CPF que aparecia integralmente no formulário. Autorizei a apresentação dessas versões no portfólio. A publicação dos arquivos PNG no GitHub ainda não foi concluída devido a uma limitação técnica na transferência dos arquivos; por enquanto, mantenho abaixo a documentação das telas. Os indicadores exibidos nos prints são estados dos registros mostrados na interface, não medições de produtividade da operação.

## Roteiro da galeria visual

A sequência foi selecionada para contar a história do produto de forma compreensível para recrutadores. As legendas abaixo indicam o papel de cada captura; a galeria de imagens será adicionada quando a transferência dos PNGs editados para o GitHub for concluída.

| Ordem | Captura | O que observar |
| --- | --- | --- |
| 1 | Tela de abertura do cofre | Proteção por senha, interface de entrada e orientações sobre backup |
| 2 | Visão geral e dashboard | Pesquisa, filtros, gráfico circular de efetividade e contadores automáticos |
| 3 | Cadastro de novo negócio | Campos opcionais, tipo de negociação e escolha da data |
| 4 | Negócios não pagos | Acompanhamento de promessas, vencimentos e ação de confirmação |
| 5 | Negócios pagos | Mudança visual de estado e feedback após confirmação manual |
| 6 | Métricas e radar de vencimentos | Barras por tipo e separação entre vencidos, vencimento hoje e a vencer |
| 7 | Save e transferência | Backup protegido por senha e importação em outro dispositivo |
| 8 | Conquista desbloqueada | Feedback de gamificação para uma confirmação registrada |
| 9 | Menu lateral | Organização da navegação, acesso a funções e escolha de tema |

As telas com registros documentam a interface e seus estados visuais, **não constituindo provas de pagamento**. A confirmação do pagamento depende do usuário e do sistema autorizado.

## 1. Cofre de acesso e proteção local

A tela de entrada apresenta o **cofre de dados**, protegido por senha. Como a aplicação foi projetada com uma abordagem *local-first*, os registros são mantidos no navegador, e a senha permite o acesso aos dados protegidos.

**O que demonstra:** atenção à privacidade, fluxo de autenticação local, mensagens de orientação e diferenciação entre dados locais e uma conta online. A própria interface alerta sobre a importância dos backups: uma senha perdida não pode ser recuperada pelo aplicativo.

## 2. Visão geral e dashboard de efetividade

Organizei a visão principal em duas áreas complementares: **lista de negócios** e **painel de indicadores**. À esquerda, é possível localizar e consultar registros; à direita, um dashboard apresenta a quantidade de negócios pagos e não pagos e a **taxa de efetividade**, com indicador circular.

**O que demonstra:** desenvolvimento de dashboard dinâmico, atualização automática de totais e percentuais a partir dos registros, apresentação visual de informações e foco na leitura rápida por quem utiliza a ferramenta.

A **confirmação de pagamento é manual**, após consulta ao sistema autorizado. O que se atualiza automaticamente são os gráficos, contadores e percentuais decorrentes dessa confirmação. O Preventivo não consulta contas, bancos ou sistemas corporativos para verificar pagamentos por conta própria.

## 3. Cadastro e classificação de negócios

Desenvolvi um formulário de cadastro com identificação do cliente, tipo de negociação, valor opcional e data prevista de pagamento. Os campos opcionais permitem registrar informações disponíveis sem exigir preenchimento desnecessário.

**O que demonstra:** formulários claros, classificação por tipo (**acordo** ou **promessa**), uso de seleção de datas e simplificação da entrada de dados.

## 4. Situação de pagamento e ação rápida

Cada cartão de negócio mostra dados essenciais, tipo, vencimento, estado do pagamento e ações de edição ou exclusão. Quando o usuário confirma um pagamento, a apresentação do cartão muda para distinguir visualmente **pago** e **não pago**.

**O que demonstra:** estados de interface coerentes, feedback visual imediato e integração entre ações do usuário e indicadores do dashboard.

## Anotações por bandeirinhas — evolução recente R2/R3/R4

Na revisão mais recente, também redesenhei o cabeçalho de cada cartão para incluir **bandeirinhas coloridas e personalizáveis**, usadas como atalhos para notas relacionadas a cada negociação. As bandeirinhas ficam na faixa superior central e o botão `+` permanece separado à direita.

O usuário pode **clicar em uma bandeirinha para ler a anotação no centro do próprio cartão**, escolher outra nota e editar por duplo clique ou botão específico; isso também favorece o uso por teclado e dispositivos de toque. As notas continuam vinculadas aos registros armazenados no cofre local criptografado. O limite documentado é de 12 bandeirinhas por negócio, com nove ícones e seis cores.

A **R4** preserva o preenchimento azul dos cartões em todos os temas — inclusive o vermelho — e aplica um contorno luminoso discreto. A R4 está consolidada como base de desenvolvimento, **sem comprovação de implantação em produção nesta auditoria**.

**Para ver a evolução e os testes:** [estudo de caso R1–R4](EVOLUCAO-R1-R4.md) · [validação da R4](VALIDACAO-R4.md).

> **Atenção à galeria:** os prints editados documentam uma versão anterior às revisões R2–R4. Não os apresento como comprovação visual das novas bandeirinhas ou das bordas luminosas. Para ilustrar visualmente a R4, usarei capturas específicas dessa revisão, com dados apropriados para divulgação.

## 5. Filtros, pesquisa e lista de negócios

A interface oferece busca por nome ou identificador e filtros de tipo e situação. Em listas extensas, o rolamento interno ajuda a manter o painel de indicadores acessível enquanto os registros são consultados.

**O que demonstra:** organização de informação, filtros de consulta e redução de etapas operacionais. Identificadores pessoais podem ser ocultados na apresentação da tela.

## 6. Desempenho por tipo e radar de vencimentos

A seção de métricas detalhadas mostra **percentuais de efetividade por tipo de negociação**, com barras de progresso, além de um **radar de vencimentos** que separa compromissos vencidos, com vencimento no dia e futuros.

**O que demonstra:** visualização de dados, segmentação de indicadores e análise de prazos em uma mesma experiência.

Esses gráficos representam o **estado dos registros da aplicação**, não estatísticas de desempenho da empresa ou resultados financeiros auditados.

## 7. Conquistas e feedback de interação

Criei mensagens de conquista que aparecem em situações específicas, como a confirmação de mais um negócio pago. A mensagem destaca o resultado registrado sem interromper permanentemente o fluxo de trabalho.

**O que demonstra:** microinterações, gamificação leve, feedback contextual e preocupação com a experiência de uso.

## 8. Exportação, importação e continuidade de trabalho

A seção **Save e transferência** permite exportar uma cópia protegida em arquivo JSON e importá-la em outro navegador ou equipamento mediante senha. A interface também apresenta orientações sobre a operação.

**O que demonstra:** portabilidade de dados, recuperação controlada, persistência local e explicações para operações sensíveis. O conteúdo não é sincronizado automaticamente em servidor público.

## 9. Navegação, organização e aparência

A aplicação possui menu lateral com acesso à visão geral, negócios, métricas, backups, senha e política de segurança, além de opções de tema visual.

**O que demonstra:** arquitetura da informação, navegação entre áreas da aplicação, consistência de componentes e personalização.

---

## Minha atuação no desenvolvimento

Identifiquei o problema na rotina profissional, defini as funcionalidades necessárias, acompanhei a implementação assistida por **GPT/Codex**, executei testes e utilizei feedback de outros profissionais para orientar melhorias. A IA foi uma **ferramenta de desenvolvimento**, não um sistema de decisão automatizada embutido no Preventivo.

Os dados permanecem armazenados localmente, e a transferência entre dispositivos depende da exportação e da importação manual de um backup criptografado. Não publico neste portfólio código interno, registros de clientes, CPF, nomes de usuários, backups ou dados da organização.

**Voltar ao [estudo de caso principal](README.md)** · [Entender a origem da solução](CONTEXTO-PROFISSIONAL.md)