---
title: Colaborar com fornecedores por meio do portal do fornecedor
description: Este tópico descreve como os agentes de compras podem usar o portal do fornecedor para colaborar com os fornecedores externos durante o processo de confirmação da ordem de compra. Estas informações se aplicam somente às versões de fevereiro de 2016 &amp; maio de 2016 do Dynamics AX.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2fa295c71fb82b4168123970fee6ba71d293e3c8
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189659"
---
# <a name="collaborate-with-vendors-by-using-the-vendor-portal"></a>Colaborar com fornecedores usando o Portal do fornecedor

[!include [banner](../includes/banner.md)]

Este tópico descreve como os agentes de compras podem usar o portal do fornecedor para colaborar com os fornecedores externos durante o processo de confirmação da ordem de compra. Estas informações aplicam-se somente às versões de fevereiro e maio de 2016 do Dynamics AX.

As informações neste tópico se aplicam somente às versões de fevereiro de 2016 e maio de 2016 do Dynamics AX. Para obter mais informações sobre a nova funcionalidade de colaboração do fornecedor, consulte [Colaboração de fornecedores com fornecedores externos](vendor-collaboration-work-external-vendors.md).  

O portal do fornecedor destina-se aos fornecedores que não têm a integração EDI (intercâmbio eletrônico de dados) com o Microsoft Dynamics AX para trocar informações de ordens de compra (OC). O portal permite que os agentes de compras enviem uma OC ao fornecedor e recebam a resposta Confirmada ou Rejeitada diretamente no Dynamics AX.  

O processo pode ser configurado de modo que uma confirmação do fornecedor confirme automaticamente a ordem. Nesse caso, o acompanhamento só será necessário ocasionalmente, quando uma ordem for rejeitada ou se a confirmação do fornecedor for registrada como uma resposta, mas o status da OC não for atualizado para **Confirmada** devido a um problema durante processo de confirmação.

## <a name="po-confirmation-and-rejection"></a>Confirmação e rejeição de OC
As OCs são preparadas no Dynamics AX. Quando você tiver uma CO com um status **Aprovado**, o enviará para o fornecedor para gerar uma solicitação de confirmação. Para chamar a atenção do fornecedor para a nova OC, você também pode usar o sistema de gerenciamento de impressão para enviar a OC por email. A OC é exibida no portal do fornecedor e inclui uma opção que o fornecedor pode usar para confirmá-la ou rejeitá-la. O fornecedor também pode adicionar comentários para comunicar informações como as alterações na OC.  

No portal do fornecedor, o fornecedor pode ver as linhas da ordem. Essas linhas incluem informações como o número do produto externo, as dimensões, as informações sobre preços, a quantidade, a data de entrega e o endereço de entrega. O fornecedor pode gerar um relatório que mostre as informações da OC e o preço total. Os encargos relevantes para o fornecedor serão mostrados se o fornecedor clicar no botão **Encargos** no cabeçalho ou nas linhas. Os fornecedores podem importar as informações da OC para seu próprio sistema usando a funcionalidade **Exportar para Excel**.  

A tabela a seguir mostra a troca comum de informações, dependendo da forma como o fornecedor reage quando você envia uma OC para confirmação:

| Tipo de resposta                                                                                                  | Resultado                                                                                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| O fornecedor confirma a ordem. O sistema está configurado para confirmar automaticamente as OCs quando o fornecedor confirmar.    | O status da ordem é atualizado para **Confirmada**. Se algo impedir que a ordem seja atualizada, a resposta do fornecedor ainda será registrada como **Confirmada**, mas o status da OC permanecerá **Em Revisão Externa**.                                                                       |
| O fornecedor confirma a ordem. O sistema não está configurado para confirmar automaticamente as OCs quando o fornecedor confirmar. | A resposta do fornecedor é registrada como **Confirmada**, mas o status da OC permanece **Em Revisão Externa**.                                                                                                                                                                                      |
| O fornecedor rejeita a ordem.                                                                                     | A resposta do fornecedor é registrada como **Rejeitada** e o status da OC permanece **Em Revisão Externa**. A rejeição foi recebida junto com o motivo e uma sugestão de alteração, como uma data de entrega alternativa. Você atualiza a OC e então envia uma nova versão para confirmação. |

## <a name="changes-to-a-po"></a>Alterações em uma OC
Quando você tiver de alterar a OC que já foi confirmada, poderá enviar uma nova OC ao fornecedor por meio do portal do fornecedor. A nova OC terá um sufixo de versão para indicar que é uma versão modificada de uma OC anteriormente comunicada. O portal do fornecedor deixa que os fornecedores controlem o histórico de cada ordem. A versão anteriormente confirmada da OC permanecerá na lista de posições confirmada até que a nova OC seja confirmada.  

Quando você cancela uma OC, o status é alterado novamente para **Aprovada**. Você deve enviar a OC novamente ao fornecedor por meio do portal do fornecedor para que ele possa confirmar ou rejeitar o cancelamento. Depois que o cancelamento for confirmado, a OC aparecerá na lista de OCs confirmadas como **Cancelada**.

## <a name="versions-status-transitions-and-change-management"></a>Versões, transições de status e gerenciamento de alterações
Quando uma OC é enviada ao fornecedor, ela é registrada no sistema como uma versão específica da OC e o status é alterado de **Aprovada** para **Em Revisão Externa**. Se a OC for alterada posteriormente, uma nova versão da OC será criada, e o status retornará a **Aprovada** (ou será alterado para **Rascunho**, se o gerenciamento de alterações estiver ativado).  

A tabela a seguir mostra um exemplo das alterações de status e versão pelas quais uma OC pode passar.

| Ação                                                   | Status e versão                                                                                    |
|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| A versão inicial da OC é criada no Dynamics AX. | O status é **Aprovada**.                                                                           |
| A OC é enviada ao portal do fornecedor.                     | Uma versão é registrada no portal do fornecedor e o status é alterado para **Em Revisão Externa**.    |
| Você faz algumas alterações que são solicitadas pelo fornecedor.  | O status é alterado novamente para **Aprovada**.                                                            |
| Você envia a nova versão da OC para o portal do fornecedor. | Uma nova versão é registrada no portal do fornecedor e o estado é alterado para **Em Revisão Externa**. |
| O fornecedor aprova a nova versão da OC.           | O status é alterado para **Confirmada**.                                                                |

Para ver as versões da OC que foram enviadas ao fornecedor e suas respostas, clique em **Diários** &gt; **Solicitações de confirmação** na OC.  

As ordens que foram enviadas ao fornecedor para a obtenção de uma resposta e com o status **Em Revisão Externa** aparecerão na lista **Ordens de compra enviadas para o portal do fornecedor, aguardando resposta** ou na lista **Ordens de compra enviadas para o portal do fornecedor, resposta requer ação**. Quando você alterar uma ordem que foi enviada ao fornecedor, para que o status seja alterado novamente para **Aprovada**, ela não aparecerá mais nessas listas. Para ver se houve uma resposta para a ordem do fornecedor, clique em **Diários** &gt; **Solicitações de confirmação**.  

Os fornecedores não precisam confirmar a OC no portal do fornecedor. Eles também podem enviar uma mensagem de email ou comunicar a aceitação de uma OC por meio de outro canais. É possível confirmar a ordem manualmente no Dynamics AX. Nesse caso, você receberá um aviso de que a ordem está sendo confirmada mesmo que não haja nenhuma resposta do fornecedor. A OC aparece no histórico de confirmação no portal do fornecedor como uma ordem confirmada aberta que não tem nenhuma resposta. Além disso, o fornecedor não terá mais a opção de confirmar ou rejeitar a OC.  

**Observação:** a versão da OC disponível para outros processos no Dynamics AX sempre será a versão mais recente, mesmo que essa versão ainda não tenha sido registrada.

### <a name="change-management"></a>Gerenciamento de alterações

Se você tiver ativado gerenciamento de alterações para uma OC, a OC passará por um fluxo de trabalho de aprovação para atingir o status **Aprovada**. Esse processo não aparece para o fornecedor.  

Quando o gerenciamento de alterações estiver ativado para uma OC, a versão será registrada quando a OC for aprovada e não quando a OC for enviada para o fornecedor ou confirmada.  

A tabela a seguir mostra um exemplo das alterações de status e versão pelas quais uma OC poderá passar quando o gerenciamento de alterações estiver ativado:


|                                                    Ação                                                     |                                                                                                                                                                                                                      Status e versão                                                                                                                                                                                                                      |
|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           A versão inicial da OC é criada no Dynamics AX.                            |                                                                                                                                                                                                            O status é <strong>Rascunho</strong>.                                                                                                                                                                                                             |
| A OC é submetida ao processo de aprovação (é um processo interno em que o fornecedor não está envolvido). |                                                                                                                        O status é alterado de <strong>Rascunho</strong> para <strong>Em Revisão</strong> para <strong>Aprovação</strong> se a OC não for rejeitada durante o processo de aprovação. A OC aprovada é registrada como uma versão.                                                                                                                        |
|                                      A OC é enviada ao portal do fornecedor                                      |                                                                                                                                                                      A versão é registrada no portal do fornecedor e o status é alterado para <strong>Em Revisão Externa</strong>.                                                                                                                                                                       |
|                            Você faz algumas alterações que são solicitadas pelo fornecedor.                            |                                                                                                                                                                                                    O status é alterado novamente para <strong>Rascunho</strong>.                                                                                                                                                                                                     |
|                              A OC é submetida ao processo de aprovação novamente.                               | O status é alterado de <strong>Rascunho</strong> para <strong>Em Revisão</strong> para <strong>Aprovação</strong> se a OC não for rejeitada durante o processo de aprovação. Alternativamente, o sistema pode ser configurado para que as alterações específicas do campo não exijam uma nova aprovação. Nesse caso, o status é primeiro alterado para <strong>Rascunho</strong> e depois automaticamente atualizado para <strong>Aprovada</strong>. A OC aprovada é registrada como uma nova versão. |
|                           Você envia a nova versão da OC para o portal do fornecedor.                            |                                                                                                                                                                    A nova versão é registrada no portal do fornecedor e o status é alterado para <strong>Em Revisão Externa</strong>.                                                                                                                                                                     |
|                                O fornecedor aprova a nova versão da OC.                                 |                                                                                                                                                     O status é alterado para <strong>Confirmada</strong> automaticamente ou quando você recebe a resposta do fornecedor e confirma a OC.                                                                                                                                                     |

## <a name="additional-resources"></a>Recursos adicionais

[Segurança de usuário do portal do fornecedor](configure-security-vendor-portal-users.md)

[Espaço de trabalho de faturamento da colaboração de fornecedores](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]