---
title: Colaboração de fornecedores com fornecedores externos
description: Este tópico explica como os agentes de compras podem colaborar com os fornecedores externos na troca de informações sobre ordens de compra e estoque de consignação.
author: Henrikan
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, VendVendorPortalInvoicePart, PurchaseOrderResponseActionRemarks, PurchVendorPortalAllResponse, PurchOrderInExternalReview, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3b679f8daed1e09c832a5d138473cccba03552f6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576967"
---
# <a name="vendor-collaboration-with-external-vendors"></a>Colaboração de fornecedores com fornecedores externos

[!include [banner](../includes/banner.md)]

O módulo **Colaboração do fornecedor** é destinado a fornecedores que não tenham integração EDI (Troca de dados eletrônica) com o Microsoft Dynamics 365 Supply Chain Management. Ele permite que os fornecedores trabalhem com ordens de compra (OCs), faturas, informações de estoque de consignação e solicitações de cotação (RFQs), e também os permitem acessar parte dos dados mestre de fornecedor. Este tópico explica como você pode colaborar com fornecedores externos que usam a interface de colaboração do fornecedor para trabalhar com OCs, RFQs e estoque de consignação. Ele também explica como habilitar um fornecedor específico para usar a colaboração do fornecedor e como definir as informações que todos os fornecedores verão ao responderem a uma OC.

Para saber mais sobre o que os fornecedores externos podem fazer na interface de colaboração do fornecedor, consulte [Colaboração do fornecedor com clientes](vendor-collaboration-work-customers-dynamics-365-operations.md).

> [!NOTE]
> As informações sobre a colaboração de fornecedor neste tópico se aplicam apenas à versão atual do Supply Chain Management. No Microsoft Dynamics AX 7.0. (fevereiro de 2016) e no aplicativo do Microsoft Dynamics AX versão 7.0.1 (maio de 2016), você colabora com fornecedores usando o módulo **Portal do fornecedor**. Para obter informações sobre o módulo **Portal do fornecedor**, consulte [Colaborar com fornecedores usando o Portal do fornecedor](collaborate-vendors-vendor-portal.md).

Para saber mais sobre como os fornecedores podem usar a colaboração do fornecedor nos processos de faturamento, consulte [Espaço de trabalho de faturamento de colaboração do fornecedor](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md). Para saber mais sobre como provisionar novos usuários de colaboração do fornecedor, consulte [Gerenciar usuários de colaboração do fornecedor](manage-vendor-collaboration-users.md).

## <a name="defining-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Definindo as informações mostradas aos fornecedores quando eles respondem a OCs

Quando os fornecedores respondem a uma OC enviada, eles veem uma das três caixas de mensagem onde devem confirmar que querem aceitar a OC, rejeitá-la ou aceitá-la com alterações. Como a informação que deve ser mostrada ao fornecedor nesse ponto pode ser específica para sua empresa, você pode especificar o texto que aparece em cada mensagem de confirmação. Por exemplo, o texto pode informar o fornecedor sobre as próximas etapas do processo ou sobre termos e condições.

Para definir o texto que é mostrado na resposta da OC, siga estas etapas

1. Na página **Informações para fornecedores em resposta a OCs**, selecione o tipo de resposta e selecione **Editar**.
2. Na caixa **Mensagem de informações**, insira informações que deve ser exibidas a fornecedores na caixa de mensagem.

Se você precisar adicionar mensagens em mais de um idioma, crie mensagens separadas e especifique o código de idioma apropriado para cada uma. A mensagem que é mostrada a cada fornecedor estará no idioma que o fornecedor usa.

## <a name="setting-the-vendor-collaboration-options-for-a-specific-vendor"></a>Definindo opções de colaboração do fornecedor para um fornecedor específico

Um administrador configura as definições gerais para a colaboração do fornecedor, como as funções de segurança disponíveis para todos os fornecedores com os quais você colabora. Porém, há também configurações que podem ser diferentes para cada conta do fornecedor. Você deve definir essas configurações.

- Habilite a colaboração do fornecedor.
- Especifique se o fornecedor deverá ver as informações sobre preço.

### <a name="enabling-vendor-collaboration"></a>Habilitando a colaboração do fornecedor

Antes que as contas de usuário possam ser criadas para um fornecedor externo, você deve configurar a conta de fornecedor para permitir que ele use a colaboração do fornecedor. Na página **Fornecedores**, na guia **Geral**, defina o campo **Ativação de colaboração**. As opções a seguir estão disponíveis:

- **Ativo (a OC é confirmada automaticamente)**– as OCs são confirmadas automaticamente, se o fornecedor as aceita sem alterações.
- **Ativo (a OC não é confirmada automaticamente)**– as OCs precisam ser confirmadas manualmente por sua organização depois que o fornecedor aceitá-las.

### <a name="specifying-whether-the-vendor-should-see-price-information"></a>Especificando se o fornecedor deverá ver as informações sobre preço

Para compartilhar as informações sobre preços das OCs por meio da interface de colaboração do fornecedor, você deve definir a opção **Valor/preços das ordens de compra** na guia **Padrões da ordem de compra** para a conta do fornecedor como **Sim**. Essas informações sobre preços incluem o preço unitário, descontos e os encargos.

## <a name="working-with-pos-when-vendor-collaboration-is-used"></a>Trabalhando com OCs ao usar a colaboração do fornecedor

### <a name="sending-a-po-to-a-vendor"></a>Enviando uma OC a um fornecedor

As OCs são preparadas no Supply Chain Management. Quando a OC tiver um status de **Aprovada**, você a enviará ao fornecedor, selecionando **Enviar para confirmação** na página **Ordem de compra**. O status da OC será mudado para **Em Revisão externa**. Depois que a PO for enviada, o fornecedor pode vê-la na página **Ordens de compra para revisão** na interface de colaboração de fornecedor. O fornecedor pode então aceitar a OC, rejeitá-la ou sugerir mudanças nela. O fornecedor também pode adicionar comentários para comunicar informações como as alterações na OC. Se quiser chamar a atenção do fornecedor para a nova OC, você também pode usar o sistema de gerenciamento de impressão para enviar a OC por email.

### <a name="confirmation-and-acceptance-of-a-po-by-a-vendor"></a>Confirmação e aceitação de uma OC por um fornecedor

Depois que um fornecedor aceita uma OC, a OC pode ser confirmada automaticamente ou pode ter que ser confirmada manualmente. O comportamento depende se o campo **Ativação de fornecedor** está definido como **Ativo (a OC é confirmada automaticamente)** ou como **Ativo (a OC não é confirmada automaticamente)** para o fornecedor.

A tabela a seguir mostra a troca comum de informações, dependendo da resposta do fornecedor quando você envia uma OC para confirmação.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Resposta do fornecedor</th>
<th>Resultado</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>O fornecedor <strong>aceita</strong> a ordem, e o Supply Chain Management é configurado para confirmar OCs automaticamente que o fornecedor aceita.</td>
<td>O status da ordem é atualizado para <strong>Confirmada</strong>. Se a ordem não puder ser atualizada por algum motivo, a resposta do fornecedor ainda é registrada como <strong>Aceita</strong>, mas o status da OC permanecerá <strong>Em Revisão externa</strong>. 

A OC que foi enviada ao fornecedor e que tem um status de <strong>Em revisão externa</strong> é atualizada com datas de entrega confirmadas nas linhas. Esta atualização inicia uma nova versão que é automaticamente definida para o status <strong>Confirmado</strong>. Quando a OC é confirmada, ela aparecerá na interface de colaboração do fornecedor.</td>
</tr>
<tr class="odd">
<td>O fornecedor <strong>aceita</strong> a ordem, mas o Supply Chain Management não está configurado para confirmar OCs automaticamente que o fornecedor aceita.</td>
<td>A resposta do fornecedor é registrada como <strong>Aceita</strong>, mas o status da OC permanece <strong>Em Revisão externa</strong>.

A OC que foi enviada ao fornecedor e que tem um status de <strong>Em revisão externa</strong> é atualizada com datas de entrega confirmadas nas linhas. Esta atualização inicia uma nova versão que é automaticamente definida para o status <strong>Em revisão externa</strong>. Em seguida, você poderá confirmar a OC manualmente.</td>
</tr>
<tr class="even">
<td>O fornecedor <strong>rejeita</strong> a ordem.</td>
<td>A resposta do fornecedor é registrada como <strong>Rejeitada</strong> e o status da OC permanece <strong>Em Revisão Externa</strong>. A rejeição é recebida junto com as anotações do fornecedor.</td>
</tr>
<tr class="odd">
<td>O fornecedor <strong>aceita</strong> a ordem <strong>com alterações</strong>. As alterações são sugeridas em nível de linha. O fornecedor pode aceitar ou rejeitar linhas individuais. Eis algumas outras alterações que o fornecedor pode sugerir:
<ul>
<li>Alterar datas ou quantidades.</li>
<li>Dividir linhas para datas de entrega ou quantidades diferentes.</li>
<li>Substituir um item.</li>
</ul>
O fornecedor não pode alterar as informações sobre preços e os encargos. Entretanto, o fornecedor pode sugerir essas alterações usando notas.</td>
<td>A resposta do fornecedor é registrada como <strong>Aceita com alterações</strong>, e o status da PO permanece <strong>Em revisão externa</strong>. Os status mostram os tipos de alterações que o fornecedor sugeriu. Para obter informações sobre o consumo automático das alterações, consulte a seção &quot;Atualizar a OC quando um fornecedor sugerir mudanças&quot; posteriormente neste tópico. </td>
</tr>
</tbody>
</table>

Você pode usar o espaço de trabalho **Preparação da ordem de compra** para monitorar as OCs respondidas pelo fornecedor. Este espaço de trabalho contém duas listas que contêm OCs com um status **Em Revisão Externa**:

- Em revisão externa requer ação
- Em revisão externa aguardando a resposta do fornecedor

### <a name="changing-a-po"></a>Alterando uma OC

Para alterar uma OC que já foi respondida por um fornecedor, você deve enviar uma nova versão da OC para o fornecedor. A nova OC terá um sufixo de versão para indicar que é uma versão modificada de uma OC anteriormente enviada. A página **Histórico de confirmações do fornecedor de ordens de compra** permite que você e seus fornecedores acompanhem o histórico de cada ordem. A versão anteriormente confirmada de uma PO permanecerá na lista de POs confirmadas até que a nova PO seja confirmada.

### <a name="canceling-a-po"></a>Cancelando uma OC

Quando você cancela uma OC, o status é alterado para **Aprovada**. Você deve enviar a OC novamente ao fornecedor, de forma que o fornecedor possa confirmar ou rejeitar o cancelamento. Depois que o cancelamento for confirmado, a OC aparecerá na lista de OCs confirmadas como **Cancelada**.

### <a name="adding-attachments-to-a-po"></a>Adicionando anexos a uma OC

Você pode adicionar anexos, como arquivos, imagens e anotações, à PO usando o sistema de gerenciamento de documentos. Anexos do tipo **Externo** estarão visíveis para o fornecedor quando você enviar a PO.

## <a name="updating-a-po-when-a-vendor-suggests-changes"></a>Atualizando uma OC quando um fornecedor sugerir mudanças

Se um fornecedor respondeu a uma OC e sugeriu mudanças, o próximo passo é processar a resposta.

No espaço de trabalho **Preparação da ordem de compra** na lista **Em revisão externa, requer ação**, você pode identificar OCs que um fornecedor aceitou com alterações. Desta lista, você também pode navegar até a resposta do fornecedor.

Em uma resposta, um fornecedor pode alterar as seguintes informações no cabeçalho:
 
- Referência de documento do fornecedor
- Modo de entrega
- Condições de entrega
- Data de entrega confirmada

O fornecedor também pode adicionar uma nota ou um anexo.

Nas linhas, o fornecedor pode alterar a quantidade e as datas de entrega, adicionar notas e anexos, rejeitar uma linha, substituir uma linha por um outro produto que é inserido como texto e dividir uma linha em entregas múltiplas. O status de uma linha, varia dependendo alterações que o fornecedor sugeriu:
    
- **Aceito com alterações**
- **Rejeitado**
- **Substituído** - neste caso, uma linha extra com o status **Substituto** será adicionada.
- **Confirmado**
- **Dividido em agenda** – Neste caso, são adicionadas linhas extras que têm um status **Linhas da agenda**.

Se uma linha não tiver nenhuma alteração, o status da linha é **Aceito**.

Em resposta, os status da linha o informam os tipos de alterações que o fornecedor fez. Além disso, todos os campos alterados aparecem em negrito para ajudá-lo a identificar as alterações.

Você pode atualizar uma OC selecionando **Processar atualização de OC** na resposta ou em uma linha de cada vez. Um campo **A atualização da OC foi processada?** no cabeçalho e nas linhas indica se o sistema processou o cabeçalho ou as linhas para atualizar a OC com alterações se originam da resposta. Você pode executar a ação **Processar atualização da OC** apenas uma vez por cabeçalho ou linha.

Nem todas as alterações sugeridas podem ser atualizadas em uma PO. Somente as atualizações no cabeçalho e as atualizações das datas e quantidades nas linhas podem ser atualizadas automaticamente na OC. Para outras alterações, você deve atualizar manualmente a PO. Nesse caso, o valor do campo **A atualização da OC foi processada?** será **Atualização manual**. Por exemplo, se um fornecedor sugerir que uma linha seja dividida em uma agenda, essa alteração será feita manualmente.

Cada linha que tem um status **Aceita** terá uma data de entrega confirmada. Quando você executa a ação **Processar atualização da OC**, essa data será atualizada na OC. Notas e anexos não serão transferidos automaticamente para a OC atual. Além disso, os contratos comerciais não são reavaliados nas linhas da OC quando você atualiza a OC por meio da ação **Processar atualização da OC**.

## <a name="po-statuses-and-versions"></a>Status e versões da PO

Esta seção descreve os diversos status que uma OC pode ter até o momento em que é confirmada. Também descreve quando as novas versões de uma OC são disponibilizadas para o fornecedor. O comportamento varia, dependendo se você usa o gerenciamento de mudanças para POs. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Versões e status se você não usar o gerenciamento de alterações

A tabela a seguir mostra um exemplo das alterações de status e versão pelas quais uma OC pode passar.

| Ação | Status e versão |
|--------|--------------------|
| A versão inicial da OC é criada no Supply Chain Management. | O status é **Aprovada**. |
| A OC é enviada ao fornecedor. | Uma versão é registrada na interface de colaboração do fornecedor e o status é alterado para **Em Revisão externa**. |
| O fornecedor envia uma resposta **Aceito com alterações**. | O status ainda é **Em Revisão externa**. |
| Você fez algumas alterações que foram solicitadas pelo fornecedor. | O status é alterado para **Aprovada**. |
| Você envia a nova versão da OC ao fornecedor. | Uma nova versão é registrada na interface de colaboração do fornecedor e o status é alterado para **Em Revisão externa**. |
| O fornecedor aceita a nova versão da OC. | O status ainda é **Em Revisão externa** a menos que a conta do fornecedor seja configurada para definir automaticamente as OCs para um status **Confirmado** quando o fornecedor as aceita. |

Os fornecedores não precisam confirmar uma OC usando a interface de colaboração do fornecedor. Eles também podem enviar um email ou comunicar a aceitação de uma OC por meio de outro canais. Em seguida, você poderá confirmar a ordem manualmente. Nesse caso, você receberá um aviso de que a ordem está sendo confirmada, mesmo que não haja nenhuma resposta do fornecedor. A OC aparecerá no histórico de confirmação como uma ordem confirmada aberta que não tem nenhuma resposta. Neste ponto, o fornecedor não terá mais a opção de confirmar ou rejeitar a OC.

> [!NOTE]
> A versão da OC disponível para outros processos no Supply Chain Management sempre será a versão mais recente, mesmo se essa versão ainda não tiver sido registrada na interface de colaboração do fornecedor.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Versões e status se você usar o gerenciamento de alterações

Se o gerenciamento de alterações estiver ativado para as OCs, as OCs passarão por um fluxo de trabalho de aprovação para atingir o status **Aprovada**. Esse processo não aparece para o fornecedor.

A tabela a seguir mostra um exemplo das alterações de status e versão pelas quais uma OC poderá passar quando o gerenciamento de alterações estiver ativado: Uma versão será registrada quando a OC for aprovada, não quando a OC for enviada ao fornecedor ou confirmada.

| Ação | Status e versão |
|--------|--------------------|
| A versão inicial da OC é criada no Supply Chain Management. | O status é **Rascunho**. |
| A OC é submetida ao processo de aprovação (O processo de aprovação é um processo interno no qual o fornecedor não está envolvido). | O status é alterado de **Rascunho** para **Em Revisão** para **Aprovação** se a OC não for rejeitada durante o processo de aprovação. A OC aprovada é registrada como uma versão. | 
| A OC é enviada ao fornecedor. | A versão é registrada na interface de colaboração do fornecedor e o status é alterado para **Em Revisão externa**. |
| Você faz algumas alterações solicitadas pelo fornecedor, manualmente ou usando a ação **Processar atualização da OC** na resposta para atualizar a OC. | O status é alterado novamente para **Rascunho**. |
| A OC é submetida ao processo de aprovação novamente. | O status é alterado de **Rascunho** para **Em Revisão** para **Aprovação** se a OC não for rejeitada durante o processo de aprovação. Alternativamente, o sistema pode ser configurado para que as alterações específicas do campo não exijam uma nova aprovação. Nesse caso, o status é primeiro alterado para **Rascunho** e depois automaticamente atualizado para **Aprovada**. A OC aprovada é registrada como uma nova versão. |
| Você envia a nova versão da OC ao fornecedor. | A nova versão é registrada na interface de colaboração do fornecedor e o status é alterado para **Em Revisão externa**. |
| O fornecedor aprova a nova versão da OC. | O status é alterado para **Confirmada** automaticamente ou quando você recebe a resposta do fornecedor e confirma a OC. |

## <a name="sharing-information-about-consignment-inventory"></a>Compartilhando informações sobre o estoque de consignação

Se você estiver usando o estoque de consignação, os fornecedores poderão usar a interface de colaboração do fornecedor para exibir informações nas seguintes páginas:

- **Ordens de compra que consomem o estoque de consignação** – as OCs para o estoque de consignação são geradas quando a propriedade do estoque é alterada do fornecedor para a sua empresa. Um recebimento de produto é lançado ao mesmo tempo. Essas OCs de consignação são exibidas somente na página **Ordens de compra que consomem o estoque em consignação**. Elas não estão incluídas na página **Todas as ordens de compra confirmadas**, no módulo **Colaboração do fornecedor**.
- **Produtos recebidos do estoque de consignação** – esta página lista todas as transações em que a propriedade dos produtos foi transferida do fornecedor para a sua empresa. Os fornecedores podem usar essas informações para faturar o cliente.
- **Estoque de consignação disponível** – esta página mostra o estoque de consignação disponível de propriedade do fornecedor que foi recebido em seu depósito.

## <a name="working-with-rfqs-when-you-use-vendor-collaboration"></a>Trabalhando com RFQs ao usar a colaboração do fornecedor

Esta seção descreve as interações entre clientes e fornecedores durante o processo de RFQ. Também explica como as informações são comunicadas aos fornecedores. Para uma visão geral básica de suporte para o processo de RFQ, consulte [Visão geral de solicitações de cotação (RFQs)](request-quotations.md).

### <a name="alternates-attachments-amendments-and-returns"></a>Alternativas, anexos, alterações e devoluções

- **Alternativas** – Em um cabeçalho de exemplos de RFQ, você pode especificar quais alternativas serão permitidas para linhas de item não catalogadas. Quando as alternativas forem habilitadas, os fornecedores poderão adicionar uma linha alternativa para cada linha solicitada.
- **Anexos** – Os anexos podem ser adicionados tanto em nível de cabeçalho como em nível de linha de um caso de RFQ. Os anexos podem ser classificados como internos ou externos. Os anexos internos podem ser exibidos apenas pelo cliente, enquanto os fornecedores podem exibir anexos externos depois que forem enviados.

    Os fornecedores também pode adicionar anexos na resposta do lance. Esses anexos podem ser exibidos pelo cliente depois que um fornecedor enviar a resposta do lance. Os anexos que os fornecedores adicionam sempre são classificados como externos. Para acessar um anexo que um fornecedor enviou com um lance, selecione **Anexos de lances** ou **Anexos de linhas de lances**.
    
    Para abrir os anexos enviados juntos com o caso de RFQ, use o símbolo de clipe de papel de manuseio de documento na resposta.

- **Alterações** – Quando uma alteração é finalizada, as respostas de lances existentes são removidas, de forma que possam ser substituídas pelos valores atualizados. As informações como a linha de preço e quantidade de respostas de lances anteriores podem ser exibidas por meio de diários no caso de RFQ.

    Para aplicar o processamento de modificação, na página **Parâmetros de compras**, na Guia Rápida **Solicitação de cotação**, defina a opção **Bloquear RFQs quando elas forem enviadas** como **Sim**. (Essa opção está definida e é obrigatória para o setor público.)

- **Devoluções** – Se um fornecedor enviou um lance, mas são necessárias mais informações ou informações modificadas para o caso de RFQ, o cliente pode devolver o lance para o fornecedor. Os dados do lance enviados anteriormente serão mantidos e o fornecedor podem fazer as alterações solicitadas sem ter que reiniciar o processo de lance.

## <a name="public-sector-extensions"></a>Extensões do setor público

Para o setor público, a funcionalidade estendida permite que um caso RFQ seja enviado aos fornecedores e publicados. Quando você publica um RFQ, qualquer pessoa que solicitar informações poderá ver o trabalho que está de acordo com as regulamentações do setor público. Todos os trabalhos disponíveis são refletidos na página de listagem **Solicitações de cotações em aberto publicadas** e as RFQ canceladas, pendentes ou concedidas podem ser exibidas na página **Solicitações de cotações fechadas publicadas**. Esses documentos também podem ser exibidos em um site fora do Supply Chain Management por meio de integrações com as seguintes entidades de dados:

- Solicitações publicadas para cotações
- Solicitações publicadas para linha de cotação
- Solicitações publicadas para anexos de cabeçalho de cotação

Essas entidades permitem que pessoas que não são usuários provisionados no Supply Chain Management, mas que tenha acesso anônimo ao site externo, exibam o trabalho disponível e fechado. Além disso, a funcionalidade estendida em **Enviar e publicar** permite ao usuário que configura os parâmetros do processo de RFQ definir um modelo de email. Quando o profissional de compras cria o caso de RFQ, ele deverá selecionar o modelo de email para enviar as informações obrigatórias aos fornecedores do caso de RFQ. 

O usuário que configura os parâmetros para o processo de RFQ pode criar vários modelos de email. Esses modelos de email podem conter o texto estático e os seguintes tokens substituição. Os tokens serão substituídos pelos valores contextuais quando um email for criado.

- %RFQCase%
- %RFQCaseName%
- %bidType%
- %inviteOnly%
- %expiryDateTime%
- %requester%
- %requestingDepartment%
- %accountnum%
- %todaysdate%
- %createddate%

Se uma alteração for necessária e for enviada após a RFQ ser enviada, a RFQ será enviada novamente a todos os fornecedores convidados. O documento publicado também será atualizado na página **Abrir solicitações publicadas para cotações**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]