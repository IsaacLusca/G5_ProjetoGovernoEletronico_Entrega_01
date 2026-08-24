# Prompts para gerar os diagramas BPMN

Os prompts abaixo correspondem aos espaços reservados no relatório. O nome do projeto deve permanecer **G5_ProjetoGovernoEletronico**, sem utilizar no diagrama o nome real da plataforma usada como inspiração.

## Prompt 1 — Busca de informações públicas

Crie uma imagem de um diagrama de processo profissional usando rigorosamente a notação BPMN 2.0, em português do Brasil, orientação horizontal, fundo branco, alta resolução e texto perfeitamente legível. Não faça infográfico, fluxograma decorativo, ilustração ou mockup de interface. Use somente símbolos BPMN padronizados: eventos circulares, tarefas com retângulos arredondados, gateways exclusivos em losango com “X”, pools/lanes, fluxos de sequência e fluxos de mensagem tracejados quando cruzarem participantes.

Título do diagrama: “Busca de informações públicas — Processo AS-IS”.

Crie três pools ou raias claramente separadas:

1. “Cidadão”;
2. “G5_ProjetoGovernoEletronico — Portal”;
3. “Fontes oficiais”.

Modele exatamente este fluxo:

- Na raia Cidadão, evento inicial “Necessidade de informação pública”.
- Tarefa do usuário “Descrever informação procurada”.
- Na raia Portal, tarefa de serviço “Receber consulta”.
- Tarefa de serviço “Interpretar consulta com apoio de IA”.
- Adicione uma anotação de texto ligada a essa tarefa: “Interpretação automática sujeita a imprecisões”.
- Tarefa de serviço “Extrair termos de busca”.
- Na raia Fontes oficiais, subprocesso expandido “Consultar fontes oficiais”, contendo três tarefas paralelas ou claramente associadas: “Consultar pedidos LAI respondidos”, “Consultar Portal da Transparência” e “Consultar Portal de Dados Abertos”.
- Retorno para a raia Portal.
- Tarefa de serviço “Organizar resultados por fonte”.
- Tarefa “Apresentar resumo, links e resultados”.
- Na raia Cidadão, tarefa “Analisar resultados”.
- Gateway exclusivo “Informação encontrada?”.
- Caminho “Sim”: tarefa “Acessar fonte oficial”, seguida do evento final “Informação consultada”.
- Caminho “Não”: tarefa “Escolher fazer pedido de acesso à informação”, seguida de evento intermediário de ligação “Iniciar registro de pedido”.

Regras visuais obrigatórias:

- Identifique as saídas do gateway com “Sim” e “Não”.
- Não inclua banco de dados, API, servidor, algoritmo específico ou arquitetura interna.
- Não use o nome da plataforma real usada como inspiração.
- Não invente etapas adicionais.
- Garanta que todas as setas tenham direção inequívoca e que nenhuma linha atravesse textos.
- Mantenha o diagrama enxuto e próprio para inserção em documentação acadêmica.

## Prompt 2 — Registro de pedido de acesso à informação

Crie uma imagem de um diagrama de processo profissional usando rigorosamente a notação BPMN 2.0, em português do Brasil, orientação horizontal, fundo branco, alta resolução e texto perfeitamente legível. Não faça infográfico, fluxograma decorativo, ilustração ou mockup de interface. Use eventos, tarefas, gateways exclusivos, pools/lanes, fluxos de sequência e fluxos de mensagem padronizados.

Título do diagrama: “Registro de pedido de acesso à informação — Processo AS-IS”.

Crie quatro pools ou raias claramente separadas:

1. “Cidadão”;
2. “G5_ProjetoGovernoEletronico — Portal”;
3. “GOV.BR”;
4. “Órgão público responsável”.

Modele exatamente este fluxo:

- Na raia Cidadão, evento inicial de ligação “Busca não atendeu à necessidade”.
- Tarefa “Iniciar pedido de acesso à informação”.
- Tarefa “Escolher tipo de informação”.
- Gateway exclusivo “Qual é o tipo de informação?” com três saídas: “Informação pública”, “Informação pessoal própria” e “Informação pessoal de terceiro”.
- Faça as três saídas convergirem em um gateway de união antes da próxima etapa. Não detalhe regras internas das opções pessoais.
- Tarefa “Pesquisar e selecionar órgão responsável”.
- Na raia Portal, tarefa “Validar órgão selecionado”.
- Retorno à raia Cidadão.
- Tarefa “Descrever pedido”.
- Adicione anotação de texto: “Evitar dados pessoais não essenciais”.
- Gateway exclusivo “Deseja anexar arquivo?”.
- Saída “Sim”: tarefa “Adicionar anexo permitido”; depois retornar ao fluxo principal.
- Saída “Não”: seguir diretamente.
- Gateway exclusivo “Deseja preservar a identidade?”.
- Saída “Sim”: tarefa “Marcar preservação de identidade”.
- Saída “Não”: seguir sem marcar.
- Unir novamente os caminhos.
- Tarefa “Revisar resumo do pedido”.
- Na raia Portal, gateway exclusivo “Cidadão autenticado?”.
- Saída “Não”: enviar fluxo de mensagem para a raia GOV.BR, tarefa “Autenticar cidadão”; receber confirmação de autenticação e retornar ao gateway ou à etapa de conclusão.
- Saída “Sim”: continuar.
- Na raia Cidadão, tarefa “Confirmar conclusão”.
- Na raia Portal, tarefa “Registrar pedido”.
- Tarefa “Gerar número de protocolo”.
- Evento intermediário de mensagem para o Cidadão: “Protocolo enviado por e-mail”.
- Fluxo de mensagem para a raia Órgão público responsável.
- Na raia Órgão, subprocesso “Analisar e responder pedido”.
- Fluxo de mensagem de resposta para o Portal.
- Na raia Portal, tarefa “Disponibilizar resposta”.
- Na raia Cidadão, tarefa “Acompanhar pedido em Meus pedidos”.
- Evento final “Resposta acessada”.

Regras visuais obrigatórias:

- Identifique todas as saídas dos gateways.
- Mostre a autenticação como interação externa com o pool GOV.BR, sem representar senha, CPF, token ou qualquer dado sensível.
- Não represente detalhes internos do órgão público, banco de dados, API ou arquitetura técnica.
- Não use o nome da plataforma real usada como inspiração.
- Não invente etapas além das descritas.
- Evite cruzamento de setas e mantenha os rótulos legíveis.
- Dê destaque visual moderado às decisões de privacidade “tipo de informação” e “preservar identidade”, sem abandonar a notação BPMN.
