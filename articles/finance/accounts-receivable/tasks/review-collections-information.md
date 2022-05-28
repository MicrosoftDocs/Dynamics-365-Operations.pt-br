---
title: Revisar informações sobre cobranças
description: Este tópico explica como revisar a informações de cobranças, bem como várias opções de instalação e transações de cobranças.
author: ShivamPandey-msft
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustCollectionsPool, SysQueryForm, CustCollectionsAgent, OMTeamSelectMemberDialog, CustVendReportInterval, CustParameters, CustAgingSnapshot, CustVendAgingBucketLookUp, CustCollectionsPoolsListPage, CustCollectionsContactPart, CustCollections
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d0cb09eb6ac455d72e9dd051065625475581416
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725027"
---
# <a name="review-collections-information"></a>Revisar informações sobre cobranças

[!include [banner](../../includes/banner.md)]

Este tópico explica como revisar a informações de cobranças, bem como várias opções de instalação e transações de cobranças. Este procedimento usa a empresa de dados de demonstração USMF.

## <a name="create-customer-pools"></a>Crie os grupos de clientes
1. No painel de navegação, Acesse **Módulos > Crédito e coleções > Configuração > Grupos de clientes**.
- Use esta página para configurar pools de clientes, que são consultas que definem um grupo de contas de clientes que podem ser exibidas e gerenciadas para cobranças ou processos de classificação por vencimento. Use os grupos de clientes para filtrar informações na página de lista **Cobranças** e nas páginas de lista relacionadas. Você também pode usar grupos de clientes para filtrar as contas de clientes que são incluídas quando os instantâneos de classificação por vencimento são criados.  
- Você pode usar os grupos de clientes para filtrar as contas de clientes que forem incluídas quando os instantâneos de classificação por vencimento forem criados.  
2. Selecione **Novo**.
3. No campo **ID do grupo**, digite um valor.
4. No campo **Descrição do grupo**, digite um valor.
5. Clique em **Selecionar critérios do grupo**.
6. No campo **Critérios**, digite um valor.
7. Selecione **OK**.
8. Selecione **Visualizar grupo de clientes**.

## <a name="create-collections-agents"></a>Crie os agentes de cobranças
1. No painel de navegação, Acesse **Módulos > Crédito e coleções > Configuração > Agentes de cobranças**.  
- Use esta página para configurar trabalhadores como agentes de cobranças e, como opção, atribuir grupos de clientes a eles. Um *agente de cobranças* é a pessoa que trabalha com clientes para ter certeza de que os pagamentos serão cobrados em tempo hábil.  
- Os agentes de cobrança que são configurados nessa página são adicionados automaticamente a uma equipe de cobranças. Se uma equipe estiver selecionada no campo **Equipe** na página **Parâmetros de contas a receber**, os agentes de cobranças serão adicionados a essa equipe. Se uma equipe não estiver selecionada, uma nova equipe chamada Cobranças será criada automaticamente e os agentes de cobranças serão adicionados à equipe.  
2. Selecione o agente desejado, então selecione **Adicionar** na página.
3. No campo **ID do grupo**, selecione o registro desejado no menu suspenso.
4. Marque ou desmarque a caixa de seleção **Grupo padrão**.
- Escolha essa opção para incluir todos os grupos de clientes nas listas de filtros para o agente de cobranças selecionado. Se essa opção não estiver selecionada, somente os grupos de clientes atribuídos ao agente de cobranças estarão disponíveis nas listas de filtros.  

## <a name="create-aging-period-definition"></a>Crie definição do período de classificação por vencimento
1. No painel de navegação, Acesse **Módulos > Crédito e coleções > Configuração > Definições de período de classificação por vencimento**.
- Você pode usar definições do período de classificação por vencimento para analisar a maturidade de contas de clientes e contas de fornecedores, com base em uma data digitada. Cada período de classificação por vencimento configurado para a definição do período de classificação por vencimento corresponde a uma coluna na página de listagem ou no formulário ou relatório quando a análise é executada.  
2. Selecione **Novo**.
3. No campo **Definição do período de classificação por vencimento**, digite um valor.
4. No campo **Descrição**, digite um valor.
- Especifique o nome, a unidade, e o intervalo do período para cada período de classificação por vencimento para incluir na definição do período de classificação por vencimento. A linha que tiver 0 (zero) no campo Unidade representará a data em que a análise será executada. As linhas antes de zero terão -1, enquanto linhas depois de zero terão 1 como uma entrada padrão no campo Unidade, mas podem ser alteradas. Selecione **Para cima** e **Para baixo** para reorganizar as linhas. A linha 0 (zero) não pode ser movida.  
- Posicione o cursor onde deseja inserir uma nova linha e, em seguida, selecione **Adicionar**.  
- Selecione um indicador para representar o período de classificação por vencimento no formulário **Cobranças** e na página de listagem. Por exemplo, você pode selecionar um indicador verde para um período atual, um indicador amarelo para um período de 30 dias de atraso e um indicador vermelho para um período de 90 dias de atraso.  
- Escolha a direção de impressão para a definição do período de classificação por vencimento. Essa seleção determina a ordem em que as colunas aparecem no Relatório de classificação por vencimento do cliente ou no Relatório de classificação por vencimento do fornecedor.  
  - Avançar - Imprime colunas na mesma ordem em que os títulos aparecem na tabela, começando com a linha superior.  
  - Voltar - Imprime colunas na ordem inversa em que os títulos aparecem na tabela, começando com a linha inferior.    

## <a name="setup-collections-parameters"></a>Parâmetros de instalação das cobranças
1. No painel de navegação, Acesse **Módulos > Crédito e coleções > Configuração > Parâmetros de contas a receber**.
2. Selecione a guia **Cobranças**.
3. Expanda ou recolha a seção **Padrões de cobrança**.
- Selecione uma definição do período de classificação por vencimento do instantâneo de classificação por vencimento padrão que será usada no formulário **Cobranças**.  
- Selecione uma equipe à qual os agentes de cobranças estão atribuídos no formulário **Agente de cobranças**. Somente as equipes que têm um tipo de equipe de Cobranças são exibidos na lista.  
4. Expanda ou recolha a seção **Dar baixa**.
- Selecione o nome do diário, que está configurado para diário-razão diários, para usar quando uma transação for baixada, usando o formulário **Cobranças** ou as páginas de listagem relacionadas.  
- Escolha o código de motivo padrão a ser usado quando as transações de baixa forem criadas, usando o formulário **Cobranças** ou as páginas de listagem relacionadas.  
- Escolha essa opção para criar uma linha de diário separada para valores de imposto quando as transações de baixa forem criadas usando a página **Cobranças** ou as páginas de listagem relacionadas. Se escolher essa opção, você poderá acompanhar mais facilmente os valores dos impostos de vendas envolvidos em transações de baixa. Você pode acompanhar os valores de impostos separadamente para ajudar a ajustar mais facilmente sua obrigação fiscal do período.  
5. Expanda ou recolha a seção **Modelo de email**.
- Selecione o modelo de email a ser usado quando você enviar uma mensagem de email usando o formulário **Email > Transações** para ação de contato no formulário **Cobranças**.  
- Selecione o modelo de email a ser usado quando você enviar um demonstrativo de cliente como um anexo em uma mensagem de email, usando o formulário **Email > Demonstrativo** para ação de contato no formulário **Cobranças**.  
- Selecione o modelo de email a ser usado quando você enviar uma mensagem de email usando o formulário **Email > Transações** para ação de vendedor no formulário **Cobranças**.  

## <a name="age-customer-balance"></a>Saldo de cliente por vencimento
1. No painel de navegação, Acesse **Módulos > Crédito e coleções > Tarefas periódicas > Classificar saldos de cliente por vencimento**.
- Selecione uma definição de período de classificação por vencimento. O processo de instantâneo de classificação por vencimento classifica as transações por vencimento de acordo com os períodos de classificação por vencimento definidos na definição do período de classificação por vencimento selecionado.  
- Selecione um grupo de clientes ou deixe esse campo em branco para criar um instantâneo de classificação por vencimento para todos os clientes. Se um grupo de clientes estiver selecionado, o processo de instantâneo de classificação por vencimento será aplicado somente para as contas de cliente que fazem parte do grupo de clientes. O grupo de clientes selecionado deve ser do tipo Instantâneo de classificação por vencimento.  
- Selecione o tipo de data no qual basear o instantâneo de classificação por vencimento.  
  - Data da transação - Classificar por vencimento cada transação com base na data da transação.    
  - Data de vencimento - Classificar por vencimento com base na data de vencimento.    
  - Data do documento - Classificar por vencimento com base na data do documento.  
- Selecione a data a ser usada como a data atual do instantâneo de classificação por vencimento. Os períodos de classificação por vencimento são calculados com base nessa data.    
  - Data de hoje - Usar a data do sistema. Use essa opção se o processo estiver configurado para ocorrer em um lote recorrente. Se você usar essa data, o lote recorrente poderá ser executado periodicamente, e a data do sistema naquele momento será usada.    
  - Data selecionada - usar uma data que você especificar. Se você escolher essa opção, insira uma data de classificação por vencimento.  
2. Selecione **OK**.

## <a name="view-aged-customer-balances"></a>Exibir saldos antigos de cliente
1. No painel de navegação, Acesse **Módulos > Crédito e cobranças > Cobranças > Saldos antigos**.
- Use esta página da lista para exibir saldos do cliente e valores antigos por período de classificação por vencimento. Essas informações ficam armazenadas em um instantâneo de classificação por vencimento. Os períodos de classificação por vencimento são determinados pela definição do período de classificação por vencimento usada. A definição do período de classificação por vencimento é tirada do grupo de clientes, se tiver sido especificada para a consulta de grupo. Se o grupo de clientes não tiver uma definição do período de classificação por vencimento, a definição do período de classificação por vencimento padrão especificada no formulário Parâmetros de contas a receber será usada.  
2. Expanda o Quadro de Fatos **Contato**. Aqui, você pode exibir informações de contato:
- O contato de cobrança do cliente.  
- Vendedor padrão do cliente.  
3. Expanda o Quadro de Fatos **Limite de crédito**.
- Use o Quadro de Fatos **Informações de crédito** para exibir as informações de limite de crédito e do saldo atual para o cliente.  

## <a name="view-customer-collections-details"></a>Exibir detalhes de cobranças de clientes
1. Verifique se o registro desejado foi selecionado.
2. Expanda os Quadros de Fatos **Endereço**, **Contato**, **Classificar por vencimento** e **Limite de crédito** para exibir as informações fornecidas.
3. No Painel de Ação, selecione **Cobrar**.
- Atualizar o instantâneo de classificação por vencimento para o cliente, usando a data atual como a data da classificação por vencimento na qual as datas de transação são comparadas. Se o instantâneo de classificação por vencimento contiver informações de várias entidade legais, o instantâneo de classificação por vencimento atualizado conterá informações sobre o mesmo conjunto de entidades legais. Os valores são armazenados na moeda contábil da entidade legal que você efetuou logon quando atualizou o instantâneo de classificação por vencimento.  
- Selecione uma definição de período de classificação por vencimento. Por padrão, a definição do período de classificação por vencimento associada ao instantâneo de classificação por vencimento do cliente é exibida. A definição do período de classificação por vencimento controla os períodos de classificação por vencimento e os valores que são mostrados nos Quadros de Fatos **Saldos antigos** e **Informações de crédito**.  
- Abre um menu com os seguintes itens:    
  - Empresa – exibe valores nos Quadros de Fatos Saldos antigos e Informações de crédito na moeda contábil da entidade legal.  
  - Cliente – Exibe valores nos Quadros de Fatos de saldos classificados por vencimento e informações de limite de crédito na moeda do cliente.  
- Selecione uma ou mais entidades legais no instantâneo de classificação por vencimento do cliente para o qual serão exibidas as informações. As entidades legais que são mostradas na lista foram selecionadas quando o instantâneo de classificação por vencimento foi criado.  
- Exiba o demonstrativo de cliente no formato do Microsoft Excel. Você pode selecionar uma data inicial do intervalo de transações a ser incluída no demonstrativo e decidir se deseja incluir somente as transações abertas ou, as transações abertas e liquidadas. Se o instantâneo de classificação por vencimento contiver informações para várias entidades legais, as transações serão incluídas para todas as entidades legais.  
- Abra o formulário **Documentos**, no qual você pode criar ou editar documentos ou anotações.  
4. No Painel de Ação, clique em **Comunicar**.  
- Abra o Outlook, onde você pode enviar uma mensagem de email para o contato especificado no campo Contato. Se um contato de cobrança não for especificado, o endereço principal do cliente será usado. Se um contato principal não for especificado, as mensagens de email serão enviadas para o primeiro endereço listado no formulário **Contatos**. As transações que são selecionadas são incluídas como um anexo. O anexo está no formato Excel e contém três planilhas. Um modelo de email para mensagens para contatos de cliente pode ser especificado no formulário **Parâmetros de contas a receber**.  
- Este botão não estará disponível se o contato que está selecionado neste formulário não tiver um endereço de email configurado.  
- Prepare uma instrução e abra o Outlook, onde você pode enviar uma mensagem de email com um demonstrativo associado ao endereço especificado no campo **Contato**. Se um contato de cobrança não for especificado, o endereço principal do cliente será usado. Se um contato principal não for especificado, as mensagens de email serão enviadas para o primeiro endereço listado no formulário **Contatos**.  
- Este botão não estará disponível se o contato que está selecionado neste formulário não tiver um endereço de email configurado.  
- Abra o Outlook, onde você pode enviar uma mensagem de email para o funcionário especificado como o representante de vendas, para o grupo de vendas atribuído ao cliente. Se as transações forem selecionadas, elas serão incluídas como um anexo. O anexo está no formato Excel e contém duas planilhas. Um modelo de email para mensagens para vendedores pode ser especificado no formulário **Parâmetros de contas a receber**.  
- Este botão não ficará disponível, se o vendedor que está exibido neste formulário não tiver um endereço de email configurado.  
- Exiba e execute ações nas transações do cliente. Se você estiver usando pagamentos centralizados, as informações para todas as entidades legais que são incluídas no instantâneo de classificação por vencimento do cliente serão incluídas. Você pode restringir as informações da entidade legal usando o botão **Empresa** em **Selecionar** grupo no painel de ação.  
- Altere o status das cobranças das transações selecionadas.    
  - Não contestado – Não ocorreu nenhuma ação de cobranças para a transação.    
  - Contestado – O cliente notificou que há um problema na transação.    
  - Promessa de pagamento – O cliente concordou em pagar o valor da transação.    
  - Resolvido – Todos os problemas com a transação foram solucionados e não será necessária nenhuma ação de cobranças adicional.  
- Abra um menu e selecione um dos seguintes itens para especificar quais transações devem ser exibidas neste formulário:    
  - Em aberto - exibe somente as transações que não foram liquidadas.    
  - Abertas e fechadas – Exibe todas as transações, liquidadas e não liquidadas.  
- Processe o pagamento selecionado com um pagamento NSF (fundos não suficientes).    
  - Este botão estará disponível apenas se a transação selecionada for um pagamento (um saldo de crédito sem uma fatura) inserido em um diário de pagamentos, uma conta bancária for atribuída à transação, e o pagamento não tiver sido cancelado anteriormente.  
- Dar baixa nas transações selecionadas.  
- Marque as transações selecionadas para liquidação umas com as outras.  
- Abra o formulário **Documento original**, no qual você pode exibir e imprimir o documento para a transação selecionada.  
- Abra um **menu** com os seguintes itens:    
  - Cobranças – exibe somente atividades criadas no formulário Cobranças.    
  - Tudo – Exibe todas as atividades do cliente, independentemente de onde as atividades foram criadas.  
- Abra um **menu** com os seguintes itens:    
  - Em aberto – exibe somente as atividades que ainda não estão fechadas.    
  - Abertas e fechadas – Exibe todas as atividades, independentemente do status.  
- Marque uma caixa de cobrança que seja atribuída ao cliente ou deixe este campo em branco. Se uma caixa for selecionada, somente as transações e as atividades associadas ao caso serão exibidas neste formulário.  
5. Selecione **Mostrar lista**.
- Selecione um conta do cliente ou aceite a entrada padrão. Por padrão, esta é a conta de cliente selecionada na página de lista ou no formulário no qual você abriu este formulário. Se você tiver aberto o formulário de uma página de lista, os clientes na lista são os clientes que estão incluídos no grupo de cobranças que é usado na página de lista.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
