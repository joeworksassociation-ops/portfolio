# Preventivo 2.0.1 — evolução do produto e experiência de uso

**Marco da versão: 6 de novembro de 2026** · **Estudo de caso para portfólio**

> Aprovei a **versão 2.0.1 como base oficial de desenvolvimento**. Também realizei a publicação da aplicação no Cloudflare Pages, conforme registrei no histórico do projeto; esta documentação não representa verificação técnica independente do deploy ou homologação corporativa.

## Contexto

Idealizei o Preventivo para reunir o acompanhamento de promessas e acordos de pagamento em uma interface que pudesse consultar rapidamente durante o atendimento. Conforme utilizei o produto e recebi feedback de outros profissionais, passei a priorizar a facilidade de registrar negócios, recuperar anotações, visualizar indicadores e evitar interrupções no fluxo.

Desenvolvi e refinei as funcionalidades com apoio de **GPT/Codex**, definindo requisitos, avaliando comportamentos e resultados, solicitando ajustes e acompanhando os testes.

## O que evoluí até a versão 2.0.1

| Área | Evolução implementada | Por que fiz a mudança |
| --- | --- | --- |
| **Anotações por negócio** | Bandeirinhas com cores, ícones e texto consultável diretamente no cartão, além de opções de edição. | Queria localizar o contexto de cada negociação sem abrir uma janela só para ler uma nota. |
| **Dashboard** | Indicadores de efetividade com animações curtas e filtros por período. | Busquei facilitar a interpretação dos resultados registrados. |
| **Cadastro** | Formulário mais compacto, com acesso aos campos necessários. | Procurei reduzir o espaço ocupado pelo cadastro sem perder informações importantes. |
| **Cadastro flutuante experimental** | Uso da API **Document Picture-in-Picture** para abrir uma janela de cadastro enquanto navego em outras páginas, quando o ambiente permite. | Queria diminuir a necessidade de alternar entre telas. Há retorno ao cadastro tradicional quando a API não está disponível. |
| **Identidade visual** | Login redesenhado, logo original FireMohawk com dimensão reduzida em 15% sem alterar sua posição, cinco temas e identificação discreta **v2.0.1**. | Procurei manter uma experiência consistente e uma identidade própria. |
| **Gamificação** | Celebração com troféu dourado, moedas e pequenas cédulas ao confirmar manualmente um pagamento. | Refinei o feedback visual para ser perceptível **sem bloquear cliques ou a navegação**. |

As melhorias foram construídas em etapas. Nas revisões **R1–R4**, concentrei-me nas etiquetas, leitura de anotações e uniformidade visual dos cartões. Em ciclos posteriores **R5 e R5.1**, refinei botões e interação das tags; na **R5.2**, as animações do dashboard; na **R5.3–R5.3.1**, o cadastro compacto/flutuante e a edição de tags; na **R5.3.2–2.0.0**, o login e a identidade visual. A **2.0.1** consolidou o novo feedback de conquista e o ajuste do tamanho do logo.

[Veja as decisões de interface das revisões R1–R4](EVOLUCAO-R1-R4.md).

## Arquitetura e proteção de dados

O Preventivo é uma aplicação web construída com **HTML, CSS, JavaScript e APIs nativas do navegador**. Os registros ficam armazenados localmente no cofre protegido por senha, com exportação e importação de backups criptografados. Não há, nessa arquitetura documentada, banco de dados remoto do próprio produto para sincronizar os registros.

A marcação de um pagamento como **pago é manual**, após consulta aos sistemas autorizados. Os gráficos e indicadores são atualizados a partir dos estados dos registros, mas **não verificam pagamentos automaticamente**. O aplicativo não usa IA para avaliar clientes; a IA participa do meu processo de desenvolvimento.

O modo Picture-in-Picture depende de navegador compatível, permissões e políticas de cada equipamento. Por isso, não o apresento como funcionalidade homologada em todos os computadores da operação.

## Validação da 2.0.1

Os registros técnicos desta revisão documentam:

- **16 de 16 cenários de interface aprovados** em Chromium, utilizando simulações de armazenamento e criptografia nessa bateria.
- **5 de 5 verificações criptográficas aprovadas** separadamente com Web Crypto real em Node.
- Verificação de sintaxe JavaScript e integridade do pacote de referência, registradas na consolidação da versão.
- Ensaios específicos da animação de troféu, moedas e cédulas, comportamento sem bloqueio de cliques, login, cofre e preferência por movimento reduzido.

Esses resultados não são equivalentes a certificação externa de segurança, teste de penetração ou validação integral da versão publicada. A funcionalidade Picture-in-Picture nativa ainda exige avaliação nos navegadores e equipamentos utilizados na operação.

Os números da revisão **R4** e os da **2.0.1** correspondem a baterias **diferentes**, com escopos próprios. Não os somo nem os apresento como se fossem a mesma execução.

## Uso prático e limites dos resultados

O Preventivo é utilizado e avaliado por aproximadamente **15 outros profissionais**, segundo o acompanhamento do projeto. Entretanto, não medi formalmente economia de tempo, aumento de produtividade ou redução de erros atribuíveis à 2.0.1; não atribuo percentuais ou valores a benefícios ainda não aferidos.

Também não apresento a publicação informada no Cloudflare Pages como comprovação de homologação corporativa.

## Imagens e privacidade

Minha [galeria de telas publicada](GALERIA-GITHUB.md) reúne **dez prints editados e autorizados para o portfólio**. Essas imagens documentam **uma versão anterior** e não devem ser confundidas com capturas da interface 2.0.1.

Neste repositório publico somente estudos de caso e material visual autorizado. Não disponibilizo o código-fonte da aplicação, pacotes de implantação, dados de clientes, backups ou credenciais.

---

[Voltar ao estudo de caso](README.md) · [Ver a galeria](GALERIA-GITHUB.md) · [Consultar a evolução anterior](EVOLUCAO-R1-R4.md)
