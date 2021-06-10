---
title: Visão geral do autoatendimento para funcionários e gerentes
description: Este artigo fornece uma visão geral do espaço de trabalho de autoatendimento para funcionários e gerentes.
author: andreabichsel
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 09efb52a76be8ee458135b013b577666a56953f7
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052112"
---
# <a name="employee-and-manager-self-service-overview"></a>Visão geral do autoatendimento para funcionários e gerentes

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo fornece uma visão geral do espaço de trabalho de autoatendimento para funcionários e gerentes.

## <a name="edit-personal-details"></a>Editar informações pessoais

Se você precisar adicionar ou alterar qualquer informação pessoal, consulte [Editar informações pessoais](hr-employee-manager-self-service-edit-personal-information.md).

## <a name="user-not-assigned-to-a-worker-record"></a>Usuário não atribuído a um registro de trabalhador

Se você não tiver vinculado seu usuário a um registro de **Trabalhador** na página **Usuários**, a seguinte mensagem será exibida:

**Sua ID de usuário não está associada ao seu registro de funcionário no sistema. Você não poderá exibir ou atualizar suas informações até que isso seja feito. Entre em contato com seu gerente ou a equipe de suporte para obter ajuda.**

Para associar um usuário a um registro do **Trabalhador**, navegue até **Usuários** e selecione o usuário. Selecione **Editar**, adicione o trabalhador correspondente no campo **Pessoa** no formulário e selecione **Salvar**. Agora você deve ter acesso ao Autoatendimento para funcionários.

## <a name="security-requirements-for-employee-and-manager-self-service"></a>Requisitos de segurança para Autoatendimento de Funcionário e Gerente

Autoatendimento de Funcionário e Gerente requer duas funções de segurança:

- Funcionários exigem a função de funcionário.
- Gerentes exigem as funções Funcionário e Gerente.

>[!NOTE]
>Você também pode usar as funções personalizadas para acessar o Autoatendimento de Funcionário e Gerente desde que tenha acesso a espaços de trabalho de Funcionário e Gerente.<br>
>O acesso do Gerenciador às informações do funcionário se baseia na hierarquia da linha da posição atual definida em Recursos Humanos.

## <a name="employee-self-service"></a>Autoatendimento para funcionários

A guia **Minhas informações** exibe as seguintes informações sobre autoatendimento para funcionários.  

### <a name="summary"></a>Resumo

**Itens de trabalho atribuídos a mim**: exibe todas as aprovações e itens de fluxo de trabalho atribuídos ao funcionário. Você pode configurar itens de fluxo de trabalho para enviar emails ao usuário.

**Questionários atribuídos a mim**: exibe todos os questionários planejados atribuídos diretamente ao funcionário ou grupo.

**Diretório da empresa**: permite que os funcionários procurem informações relacionadas a indivíduos na organização. Informações de contato públicas estão disponíveis para todos os funcionários. O diretório da empresa é restrito à empresa na qual o funcionário se conectou.

**Calendário da equipe**: mostra as informações de calendário da sua equipe. Para obter mais informações, consulte [Exibir calendários da equipe e da empresa](hr-employee-self-service-calendar.md).

### <a name="my-career-information"></a>Informações da minha carreira

A seção **Minhas informações de carreira** do autoatendimento para funcionários contém cartões relacionados a licenças e ausências, gerenciamento de desempenho, competências, benefícios, tarefas e anexos.

O cartão **Saldos de folgas** exibe os saldos de todos os planos registrados. Este cartão prevê seu saldo com base no seu método de competência. É possível inserir e enviar solicitações de folga, que passarão por um processo de fluxo de trabalho de aprovação. Para obter mais informações sobre licenças e ausências, consulte [Visão geral de licença e ausência](hr-leave-and-absence-overview.md).

O cartão **Tarefas** exibe as tarefas atribuídas a você e permite visualizá-las e gerenciá-las.

O cartão **Próximo curso registrado** exibe o próximo curso no qual você está registrado. É possível exibir e se inscrever em qualquer curso aberto. Todos os cursos abertos para inscrição têm o status **Iniciado** e permitem que os funcionários se registrem automaticamente nesse cartão. Dependendo das configurações da sua organização, sua inscrição no curso talvez passe por um processo de aprovação.

O cartão **Certificados** exibe o certificado e a data de vencimento do certificado com expiração mais próxima da data atual. Você pode atualizar, adicionar ou remover certificados. Dependendo das configurações da sua organização, as atualizações de certificado talvez passem por um processo de aprovação.

O cartão **Próxima revisão agendada** exibe sua próxima avaliação de desempenho. Você pode iniciar uma nova revisão nesse cartão. Seu gerente ou representante de HR também pode iniciar revisões. Dependendo das configurações da sua organização, você também poderá visualizar, atualizar e enviar revisões de saída nesse cartão.

Você pode gerenciar suas metas com o cartão **Metas de desempenho**. Esse cartão exibe o número de metas que você tem em cada status (**Não iniciado**, **Em curso** e **Requer aperfeiçoamento**). Você pode criar, atualizar e remover metas, dependendo da segurança baseada em função atribuída. Se desejar, você pode adicionar novas metas de grupos ou modelos. Gerentes e HR também podem criar metas em nome dos funcionários e determinar o grau de detalhamento que cada meta terá. Gerentes e funcionários podem colaborar em metas e atualizar atividades, medidas e status. Você também pode incluir anexos.

Você pode visualizar suas habilidades existentes no cartão **Habilidades**. Você pode atualizar habilidades, adicionar novas ou remover as que não são mais relevantes. Dependendo das configurações da sua organização, as alterações nas suas habilidades talvez passem por um processo de aprovação.

Você pode visualizar sua remuneração atual por meio do cartão **Remuneração**. Selecione **Mostrar** para visualizar seu pagamento anual e o valor do último aumento. Se você trabalha em mais de uma empresa, cada valor anual é exibido no cartão. Para visualizar seu histórico de remuneração detalhado, selecione o valor do salário anual para abrir o formulário **Histórico de remuneração fixa e variável**. Remunerações futuras não são exibidas nesse formulário. Se você tiver mais de um trabalho, poderá alternar entre empresas nesse formulário para visualizar seu histórico de remuneração sem necessidade de se conectar a cada empresa.

Visualize e gerencie documentos com o cartão **Anexos**. Você pode gerenciar todos os anexos **Externo**. HR e funcionários podem adicionar anexos por meio do autoatendimento para funcionários ou do formulário **Trabalhador**. Os anexos estão definidos como **Externo** por padrão.

### <a name="additional-information"></a>Informações adicionais da Nf-e

Esta seção fornece links para outras áreas de autoatendimento para funcionários, semelhantes à seção **Minhas informações de carreira**.

Inscreva-se nos benefícios por meio do link **Benefícios**. Para obter mais informações sobre gerenciamento de benefícios, consulte [Visão geral dos benefícios](hr-benefits-management-overview.md)

Em **Desempenho**, você pode selecionar **Diários de desempenho** para criar entradas de diário de desempenho para usar em metas e revisões de desempenho. Você pode selecionar **Enviar comentários** para fornecer comentários a outros funcionários da sua organização. Dependendo das configurações da sua organização, os emails podem ser enviados ao destinatário, remetente e gerentes. Você pode enviar comentários para todos os funcionários da organização. O envio de comentários não é restrito pela empresa.

Em **Competências**, você pode fazer alterações em **Cursos**, **Formação**, **Posições de confiança** e **Experiência profissional**. Dependendo das configurações da sua organização, as atualizações dessas competências talvez passem por um processo de aprovação.

É possível ver os detalhes do trabalho em **Organização**. Os detalhes do trabalho incluem habilidades, certificados e áreas de responsabilidade do seu cargo principal. Você também pode ver qualquer equipamento emprestado com check-out para você. Dependendo das configurações da sua organização, as alterações no equipamento emprestado talvez passem por um processo de aprovação.

Em **Questionário**, você poderá ver os questionários preenchidos. Também poderá ver questionários da empresa inteira que não foram concluídos. Você poderá optar por preencher um questionário a qualquer momento. O autor do questionário pode determinar o prazo e a quem o questionário se aplica.

Você pode configurar links definidos pelo usuário em **Parâmetros do Human Resources**. Por exemplo, você pode definir links para demonstrativos de pagamento, documentação de fechamento do exercício ou soluções externas. Esses links são exibidos na parte inferior desta seção, mas você pode movê-los usando a personalização.

Você também pode criar guias adicionais incorporando o Power Apps no espaço de trabalho de autoatendimento para funcionários. Use o menu **Configurações** para personalizar a página com qualquer Power Apps. No menu **Configurações**, você pode optar por adicionar um Power App, concluir os detalhes e inserir o aplicativo. Por padrão, o Power Apps aparece como a primeira guia na sequência. Você pode alterar a ordem usando a personalização padrão.

## <a name="my-team"></a>Minha equipe

A guia **Minha equipe** exibe as seguintes informações sobre o autoatendimento para gerentes. Apenas os gerentes podem acessar a guia **Minha equipe**.

### <a name="personnel-actions"></a>Ações de pessoal

As ações de pessoal são exibidas com base nas opções de configuração em **Parâmetros compartilhados de recursos humanos** e **Parâmetros do Human Resources**. Quando habilitadas para **Trabalhadores**, as ações de pessoal habilitam novas opções de menu, incluindo:

- **Solicitar novo funcionário**
- **Solicitar novo prestador de serviço**
- **Solicitar reatribuição do trabalhador**
- **Solicitar demissão**
- **Solicitar alteração de remuneração**

É possível configurar essas opções para passar por um fluxo de trabalho de revisão e aprovação opcional.

Habilitar **Ações de posição** ativa as seguintes opções:

- **Solicitar nova posição**
- **Solicitar alteração de detalhes da posição**

Também é possível configurar essas opções para passar por um fluxo de trabalho de revisão e aprovação opcional.

### <a name="summary"></a>Resumo

As informações na seção **Resumo** dependem das opções que o HR selecionou em **Parâmetros de recursos humanos**. Na guia **Autoatendimento para gerentes** da página **Parâmetros do Human Resources**, você pode configurar opções para exibir registros expirados e posições abertas. A habilitação dessas opções determina o que os gerentes podem ver na seção **Resumo**.

Você pode configurar os seguintes blocos para gerentes:

- **Certificados da minha equipe em vencimento**
- **Números de identificação em vencimento de minha equipe**
- **Períodos de experiência em vencimento para minha equipe**
- **Triagens em vencimento para minha equipe**
- **Testes em vencimento para minha equipe**
- **Posições em aberto para subordinados diretos e/ou estendidos**
- **Solicitações de folga pendentes para minha equipe**
- **Avaliação de habilidades da equipe**
- **Análise de lacuna de habilidades**
- **Diários de desempenho de equipe**
- **Metas de desempenho da equipe**
- **Revisões de desempenho da equipe**
- **Trabalhadores saindo da empresa**

É possível configurar as seguintes opções para os gerentes fazerem alterações ou adicionar solicitações de licença em nome de seus subordinados diretos:

- Certificados
- Cursos
- Itens de empréstimo
- Habilidades
- Solicitações de licença e ausência

### <a name="my-team-information"></a>Informações da minha equipe

As informações da minha equipe permitem que os gerentes visualizem e atualizem subordinados diretos e estendidos. Para acessar subordinados estendidos, selecione o funcionário com subordinados diretos e escolha **Exibir equipe** no cartão. Todas as mesmas opções se aplicam a subordinados estendidos como subordinados diretos. 

#### <a name="summary-tab"></a>Guia Resumo

A guia **Resumo** fornece uma visão rápida dos seus subordinados diretos. Se um subordinado direto também tiver trabalhadores se reportando a ele, o cartão exibirá o número de subordinados diretos na seção superior, juntamente com o botão **Exibir equipe**. As opções acima de cada cartão se aplicam ao funcionário selecionado. Por exemplo, se você desejar inserir uma solicitação de licença em nome de um funcionário, selecione o funcionário e escolha **Solicitar folga** acima dos cartões. 

Se você selecionar o botão **Detalhes** após selecionar um funcionário, as seguintes opções serão exibidas:

- **Certificados**
- **Remuneração**
- **Cursos**
- **Revisões**
- **Folga**
- **Itens emprestados**
- **Metas de desempenho**
- **Cursos registrados**
- **Habilidades**
- **Enviar comentários**

Dependendo das configurações da sua organização, você pode fazer alterações ou exibir apenas.

#### <a name="position-tab"></a>Guia Posição

A guia **Posições** fornece uma visão resumida dos funcionários em sua posição principal. Nome, bloco e departamento são exibidos na área de cabeçalho de cada cartão. Este cartão inclui:

- **Aniversário de tempo de serviço**: exibido na seção de resumo do trabalhador do formulário de trabalho
- **Anos de serviço**: calculados com base na data de início do trabalho do funcionário
- **Número de posições anteriores**: com base no histórico de posições, a seleção desse número abre a exibição detalhada de todas as posições anteriormente ocupadas
- **Data de nascimento**: o mês e o dia da data de nascimento do funcionário

Você pode visualizar dados de posição para subordinados diretos e estendidos.

#### <a name="compensation-tab"></a>Guia Remuneração

A guia **Remuneração** exibe o salário anual do funcionário. Um identificador da empresa é exibido abaixo do valor do salário. Se um funcionário tiver mais de um trabalho e estiver sendo pago por várias pessoas jurídicas, ele terá vários planos de remuneração. Para ver todos os planos de remuneração entre entidades legais sem alternar entre empresas, você deve habilitar a remuneração cruzada em **Recursos Humanos > Parâmetros compartilhados > Acesso avançado > Habilitar a remuneração entre empresas**.

Para visualizar o histórico de remuneração, selecione o valor do salário para abrir o formulário **Detalhes**. Somente os registros de remuneração fixa e variável atuais e históricos são exibidos no formulário **Remuneração**. Se um funcionário tiver mais de um emprego, você poderá alternar entre as empresas para exibir o histórico de remuneração em cada empresa ou habilitar a remuneração cruzada da empresa nos parâmetros compartilhados de recursos humanos para exibir todos os planos de remuneração.

Você pode visualizar a remuneração dos subordinados diretos e estendidos.

#### <a name="leave-and-absence-tab"></a>Guia Licença e ausência

A guia **Licença e ausência** exibe os principais saldos dos funcionários que têm atividade. Para executar uma ação ou exibir uma lista completa de atividades, selecione **Detalhes** e, em seguida, selecione **Folga**. No formulário **Folga**, é possível visualizar saldos, solicitações, folgas aprovadas e previsão de saldos para ajudar os funcionários a gerenciar melhor o tempo. Dependendo das configurações da sua organização, você também pode solicitar uma folga para seus subordinados diretos e estendidos.

#### <a name="performance-goals-tab"></a>Guia Metas de desempenho

A guia **Metas de desempenho** resume as metas de desempenho por status. Selecione um número para um status ou selecione metas de desempenho em **Detalhes** para ver todas as metas de um funcionário. Gerentes e funcionários podem atualizar as metas conforme necessário durante a meta.

Os gerentes podem ver todas as metas de sua equipe por meio do bloco **Metas de desempenho da equipe** na seção **Resumo** da **Minha equipe**.

#### <a name="reviews-tab"></a>Guia Revisões

A guia **Revisões** resume as revisões que o funcionário tem em cada estado: **Em andamento**, **Pronto para revisão** e **Revisão final**. Para acessar a revisão de um funcionário, selecione o botão **Detalhes** e selecione as revisões nas quais colaborar. Com base na posição de uma revisão dentro do processo do fluxo de trabalho, você poderá verificar se a revisão está disponível para atualização. 

Você poderá ver todas as revisões da sua equipe por meio do bloco **Avaliações de desempenho da equipe** na seção **Resumo** de **Minha equipe**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]