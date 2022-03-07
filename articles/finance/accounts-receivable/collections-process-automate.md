---
title: Automação do processo de cobranças
description: Este tópico descreve a configuração de estratégias do processo de cobranças que identificam automaticamente as faturas de cliente que exigem um lembrete por email, uma atividade de cobrança (como um telefonema) ou uma carta de cobrança a ser enviada ao cliente.
author: JodiChristiansen
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 59db852024faf457db7ac145b67619b31555aaf2
ms.sourcegitcommit: 3f6cbf4fcbe0458b1515c98a1276b5d875c7eda7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "7486860"
---
# <a name="collections-process-automation"></a>Automação do processo de cobranças

[!include [banner](../includes/banner.md)]

Este tópico descreve a configuração de estratégias do processo de cobranças que identificam automaticamente as faturas de cliente que exigem um lembrete por email, uma atividade de cobrança (como um telefonema) ou uma carta de cobrança a ser enviada ao cliente. 

Geralmente as organizações gastam uma quantidade significativa de tempo pesquisando relatórios de saldo antigos, contas de clientes e faturas em aberto para saber quais clientes devem ser contatados sobre uma fatura em aberto ou um saldo de conta. Essa pesquisa tira tempo do agente de cobrança que seria gasto na comunicação com os clientes para cobrar saldos vencidos ou resolver contestações de faturas. A automação do processo de cobranças permite configurar uma abordagem baseada em estratégias para o processo de cobrança. Isso ajuda a aplicar as atividades de cobrança consistentemente, fornecendo lembretes por email personalizados ou processo programado para enviar cartas de cobrança. 

## <a name="collections-process-setup"></a>Configuração do processo de cobranças
Você pode usar a página **Configuração do processo de cobranças** (**Crédito e cobranças > Configuração > Configuração do processo de cobranças**) para criar um processo de cobranças automatizado que vai agendar atividades, enviar mensagens de email e criar e lançar cartas de cobrança de clientes. As etapas do processo são baseadas na fatura em aberto principal ou mais antiga. Cada etapa usa essa fatura para determinar qual comunicação ou atividade deve ocorrer com um cliente específico.  

Normalmente, as equipes de cobrança enviam um aviso antecipado relacionado a cada nota fiscal pendente para que um cliente seja notificado quando a fatura está prestes a vencer. A seleção de **Pré-cobrança** pode ser definida para permitir que uma etapa de cada hierarquia de processo seja ativada para cada fatura, à medida que o tempo de duração da fatura atinge essa etapa.

### <a name="process-hierarchy"></a>Hierarquia de processos
Cada grupo de clientes só pode ser atribuído a uma hierarquia de processos. A classificação hierárquica dessa etapa identifica qual processo terá precedência se um cliente for incluído em mais de um grupo com uma hierarquia de processos atribuída. A ID do grupo determina quais clientes serão atribuídos ao processo. Cada hierarquia que é configurada somente pode ser atribuída a uma automação do processo.

Os dias silenciosos são usados para garantir que um cliente não seja contatado com muita frequência pelo processo automatizado. Por exemplo, se os dias silenciosos forem definidos como dois, um cliente não será contatado pelo processo automatizado por pelo menos dois dias, mesmo se a fatura principal original tiver sido integralmente liquidada. 

Para excluir clientes da automação de processos, se o saldo por vencimento do cliente ou o valor da nota fiscal for menor que um valor definido, selecione **Saldo de classificação por vencimento do cliente menor que** ou **Valor da fatura menor que** no campo **Excluir do processo** e insira o valor.

Marque **Usar previsão** para criar atividades de cobrança usando Previsões de pagamento do cliente. As atividades criadas usarão o modelo da Atividade das **Previsões de pagamento** na página **Parâmetros de contas a receber**, guia **Automação do processo de cobranças**. 

### <a name="process-details"></a>Detalhes do processo
Clique em **Novo** para adicionar um novo detalhe de processo à hierarquia. A **Descrição** é usada para identificar a finalidade ou o nome da etapa na hierarquia. Selecione o **Tipo de ação** para definir a etapa que vai criar uma atividade, enviar um email ou criar uma carta de cobrança. 

- O **Documento comercial** define o modelo usado para criar o tipo de ação. Este documento pode ser um modelo de atividade, um modelo de email ou uma carta de cobrança enviado para cada cliente. A automação de processos de cobrança somente cria cartas de cobrança por cliente, independentemente de como os outros parâmetros de cobranças são definidos.
- **Quando** define a etapa do processo que ocorrerá antes ou depois da data de vencimento da fatura (mais antiga) e é usada junto com o número exibido na coluna **Dias em relação à data de vencimento da fatura**. 
- Marque a opção **Pré-cobrança** para criar uma ação para cada fatura em uma etapa de uma hierarquia de processos. Normalmente, as ações de pré-cobrança são um aviso antecipado relacionado as faturas pendentes para que um cliente seja notificado quando a fatura estiver prestes a vencer. Pré-cobrança só pode ser marcada para uma atividade por hierarquia. Quando você selecionar um tipo de ação de email, o destinatário será usado para definir se a mensagem de e-mail é enviada a um contato de cliente, grupo de vendas ou agente de cobranças. 
- Em seguida, o valor no campo **Contato de finalidade comercial** determinará qual contato da conta desse cliente receberá a comunicação.

### <a name="business-document-details"></a>Detalhes do documento comercial
Os detalhes do documento comercial variarão com base no tipo de ação selecionado nos detalhes do processo. Quando o tipo de ação for uma atividade, os detalhes do modelo de atividade serão exibidos. Esses detalhes incluem o nome do modelo de atividade, o tipo de atividade que será criado, a finalidade da atividade, o número de dias agendados para concluir a atividade e os detalhes da atividade. Essa atividade será vinculada à fatura principal que informa ao destinatário a ação necessária para concluí-la.

Se o tipo de ação for um email nos detalhes do processo, essa seção conterá duas Guias Rápidas. A primeira é usada para definir a ID do modelo, a descrição do email, o idioma padrão, o nome de usuário que será atribuído às mensagens de email enviadas automaticamente e o endereço de email dos remetentes associados. A segunda permitirá que o corpo do email seja criado após os valores nos campos **Idioma** e **Assunto** serem salvos selecionando **Editar**. Isso abrirá uma janela que permite carregar conteúdo HTML. 

> [!Note]
> Você pode salvar uma mensagem de email do Outlook que contém o corpo do texto da comunicação no formato HTML. Em seguida, você poderá carregar o conteúdo da mensagem para implementar o modelo. <br> <br> Se o tipo de ação da carta de cobrança for selecionado, não haverá uma seção de detalhes do documento comercial na página de configuração.

Use o botão **Histórico do processo de cobranças** para exibir o histórico recente da hierarquia de processos selecionada. 

Clique na ação **Atribuição de processo de cobranças** para exibir os clientes atribuídos a um processo de cobranças. Use **Visualizar atribuição do cliente** para exibir a hierarquia a que um cliente específico está atribuído. Use **Visualizar atribuição de processo** para visualizar os clientes que serão atribuídos a uma hierarquia quando ela for executada. Clique em **Atribuição manual** para exibir clientes que foram atribuídos manualmente a um processo ou selecione clientes a serem atribuídos a um processo.

Clique na ação **Processar simulação** para visualizar as ações que serão criadas, se a automação do processo selecionada for executada neste momento. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
