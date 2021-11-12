---
title: Criar modelos de email para eventos transacionais
description: Este tópico descreve como criar, carregar e configurar modelos de email para eventos transacionais no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 69ba8821cde6788d6e0accb37288f92acdfc776c
ms.sourcegitcommit: 6bf9e18989e6d77497a9dda1c362f324b3c2fbf2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2021
ms.locfileid: "7713788"
---
# <a name="create-email-templates-for-transactional-events"></a>Criar modelos de email para eventos transacionais

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tópico descreve como criar, carregar e configurar modelos de email para eventos transacionais no Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce fornece uma solução pronta para o envio de emails que alertam clientes sobre eventos transacionais. Por exemplo, os emails podem ser enviados quando uma ordem é feita, quando está pronta para retirada ou quando for enviada. Este tópico descreve as etapas para criar, carregar e configurar os modelos de email usados para enviar emails transacionais.

## <a name="notification-types"></a>Tipos de notificação

As notificações podem ser configuradas para informar os clientes por email quando ocorrem eventos específicos como parte da ordem e do ciclo de vida do cliente. Para configurar as notificações, você deve mapear um modelo de email para um tipo de notificação criando um perfil de notificação por email no Commerce. Para obter mais informações sobre como configurar perfis de notificação por email, consulte [Configurar um perfil de notificação por email](email-notification-profiles.md).

O Dynamics 365 Commerce oferece suporte aos seguintes tipos de notificação:

### <a name="order-created"></a>Ordem criada

O tipo de notificação *ordem criada* é disparado quando uma nova ordem de venda é criada na matriz do Commerce.

> [!NOTE]
> O tipo de notificação de ordem criada não é disparado para transações cash and carry que ocorrem em um terminal de ponto de venda (PDV). Nesse caso, um recibo enviado por email e/ou impresso é gerado. Para obter mais informações, consulte [Enviar recibos por email no Modern POS (MPOS)](email-receipts.md).

### <a name="order-confirmed"></a>Ordem confirmada

O tipo de notificação *ordem confirmada* é disparado quando um documento de confirmação da ordem é gerado para uma ordem de venda na matriz do Commerce.

### <a name="picking-completed"></a>Separação concluída

O tipo de notificação *separação concluída* é disparado quando uma lista de separação de uma ordem é marcada como concluída na matriz do Commerce.

> [!NOTE]
> O tipo de notificação de separação concluída não é disparado quando um item é marcado como separado em um terminal de PDV.

### <a name="packing-completed"></a>Remessa concluída

O tipo de notificação *remessa concluída* é disparado quando uma guia de remessa de uma ordem é marcada como concluída na matriz do Commerce em um terminal de PDV.

O tipo de notificação de remessa concluída oferece suporte aos espaços reservados para email adicionais a seguir para facilitar a "ordem pronta para retirada" e a funcionalidade de pesquisa de ordens de emails transacionais.

| Nome do espaço reservado    | Finalidade |
| ------------------- | ------- |
| `pickupstorename`     | O nome da loja em que a ordem está disponível para retirada. |
| `pickupstoreaddress`  | O endereço da loja em que a ordem está disponível para retirada. |
| `pickupstorehourfrom` | O horário de abertura da loja de retirada. |
| `pickupstorehourto`   | O horário de fechamento da loja de retirada. |
| `pickupchannelid`     | A ID do canal de armazenamento da loja de retirada. |
| `packingslipid`      | A ID da guia de remessa da ordem que será retirada. |
| `confirmationid`      | A ID da confirmação de ordem da ordem que será retirada. (Às vezes, essa ID é referida como ID de referência do canal.) |

Para obter mais informações sobre os recursos de check-in e pesquisa de ordens do cliente, consulte [Configurar detecção de área geográfica e redirecionamento](geo-detection-redirection.md) e [Habilitar pesquisa de ordem para finalização de compra do convidado](order-lookup-guest.md).

### <a name="order-ready-for-pickup"></a>Ordem pronta para retirada

O tipo de notificação *ordem pronta para retirada* é disparado quando uma ordem é marcada como embalada e o modo de entrega é definido como **retirada pelo cliente** em uma ou mais linhas da ordem.

> [!NOTE]
> O tipo de notificação de ordem pronta para retirada foi preterido em favor do tipo de notificação de remessa concluída. Esse tipo de notificação é personalizado pelo modo de entrega.

### <a name="order-shipped"></a>Ordem remetida

O tipo de notificação *ordem enviada* é disparado quando uma ordem com um modo de entrega que não seja na loja é faturada.

> [!NOTE]
> O tipo de notificação de ordem enviada foi preterido em favor do tipo de notificação de ordem faturada. Esse tipo de notificação é personalizado pelo modo de entrega.

### <a name="order-invoiced"></a>Ordem faturada

O tipo de notificação *ordem faturada* é disparado quando uma ordem é faturada no PDV ou na matriz do Commerce.

### <a name="issue-gift-card"></a>Emitir cartão-presente

O tipo de notificação *emitir cartão-presente* é disparado quando uma ordem de venda que contém um produto do tipo de cartão-presente é faturada.

> [!NOTE]
> O email de notificação de emissão de cartão-presente é enviado ao destinatário do cartão-presente. O destinatário do cartão-presente é especificado na matriz do Commerce, em uma linha da ordem de venda individual na guia **Remessa** em **Detalhes da linha**. Ele pode ser especificado manualmente ou de forma programática.

O tipo de notificação de emissão de cartão-presente oferece suporte aos seguintes espaços reservados adicionais:

| Nome do espaço reservado      | Finalidade |
| --------------------- | ------- |
| `giftcardnumber`        | O número do cartão-presente para produtos do tipo de cartão-presente. |
| `giftcardbalance`       | O saldo do cartão-presente para produtos do tipo de cartão-presente. |
| `giftcardmessage`       | A mensagem do cartão-presente para produtos do tipo de cartão-presente. |
| `giftcardpin`         | O PIN (número de identificação pessoal) do cartão-presente para produtos do tipo de cartão-presente. (Este espaço reservado é específico de cartões-presente externos.) |
| `giftcardexpiration`    | A data de vencimento do cartão-presente para produtos do tipo de cartão-presente. (Este espaço reservado é específico de cartões-presente externos.) |
| `giftcardrecipientname` | O nome do destinatário do cartão-presente para produtos do tipo de cartão-presente. |
| `giftcardbuyername`     | O nome do comprador do cartão-presente para produtos do tipo de cartão-presente. |

Para obter mais informações sobre vales-presentes, consulte [Vales-presente digitais de comércio eletrônico](digital-gift-cards.md) e [Suporte a vales-presentes externos](dev-itpro/gift-card.md).

### <a name="order-cancellation"></a>Cancelamento da ordem

O tipo de notificação *cancelamento da ordem* é disparado quando uma ordem é cancelada na matriz do Commerce.

### <a name="customer-created"></a>Cliente criado

O tipo de notificação *cliente criado* é disparado quando uma entidade de cliente é criada na matriz do Commerce.

### <a name="b2b-prospect-approved"></a>Cliente potencial B2B aprovado

O tipo de notificação *cliente potencial B2B aprovado* é disparado quando uma solicitação de integração de um cliente potencial é aprovada na matriz do Commerce. Para obter mais informações sobre como aprovar ou rejeitar clientes potenciais B2B, consulte [Configurar o usuário administrador para um novo parceiro comercial](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

O tipo de notificação de aprovação de cliente potencial B2B oferece suporte aos seguintes espaços reservados adicionais:

| Nome do espaço reservado | Finalidade                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`       | O primeiro nome do cliente potencial B2B conforme inserido no aplicativo. |
| `lastname`         | O sobrenome do cliente potencial B2B conforme inserido no aplicativo. |
| `company`          | O nome da empresa do candidato conforme inserido no aplicativo. |
| `email`            | O endereço de email do cliente potencial conforme inserido no aplicativo.   |
| `zipcode`          | O CEP do endereço principal do cliente potencial. |
| `comments`         | O comentário inserido pelo cliente potencial no aplicativo. |
| `storename`        | O nome do canal em que o cliente potencial foi criado. |
| `storeurl`         | Vazio por padrão. Uma extensão personalizada deve ser criada para que este espaço reservado seja usado. |

### <a name="b2b-prospect-approved"></a>Cliente potencial B2B aprovado

O tipo de notificação *cliente potencial B2B rejeitado* é disparado quando uma solicitação de integração de um cliente potencial é rejeitada na matriz do Commerce. Para obter mais informações sobre como aprovar ou rejeitar clientes potenciais B2B, consulte [Configurar o usuário administrador para um novo parceiro comercial](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

O tipo de notificação de rejeição de cliente potencial B2B oferece suporte aos seguintes espaços reservados adicionais:

| Nome do espaço reservado | Finalidade                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`        | O primeiro nome do cliente potencial B2B conforme inserido no aplicativo. |
| `lastname`         | O sobrenome do cliente potencial B2B conforme inserido no aplicativo. |
| `company`          | O nome da empresa do candidato conforme inserido no aplicativo. |

## <a name="create-an-email-template"></a>Criar um modelo de email

Para poder mapear um evento transacional específico para um modelo de email, você precisa criar o modelo.

Para criar um modelo de email, siga estas etapas.

1. No Commerce Headquarters, acesse **Varejo e Comércio \> Configuração do Headquarters \> Modelos de email da organização** ou **Administração da organização \> Configuração \> Modelos de email da organização**.
1. Selecione **Novo**.
1. Em **Geral**, defina os seguintes campos:

    - **ID do email** – a ID do email é o identificador exclusivo de um modelo. É o valor exibido ao selecionar um modelo a ser mapeado para um evento.
    - **Descrição do email** – você pode usar este campo opcional para fornecer uma descrição do modelo. O valor inserido aparece somente em Commerce headquarters.
    - **Nome do remetente** – o nome inserido aparece no campo "de" da maioria dos clientes de email.
    - **Email do remetente** – insira o endereço de email que deve ser usado para emails enviados usando esse modelo.
    - **Código do idioma padrão** – esse campo especifica a versão localizada do email enviado por padrão, caso nenhum idioma seja especificado pelo canal que invoca esse modelo.

1. Em **Conteúdo da mensagem de email**, selecione **Novo**.
1. No campo **Idioma**, insira o idioma do modelo de email. Você poderá adicionar mais idiomas e modelos localizados posteriormente.
1. No campo **Assunto**, insira o assunto do email que deve aparecer no campo de assunto do email.
1. Selecione **Editar** para carregar seu modelo de email.

## <a name="create-an-email-message-body-by-using-html"></a>Crie um corpo de mensagem de email usando HTML

O corpo da mensagem do email é composto em HTML. Você pode usar qualquer layout, estilo e marca permitidos por HTML e CSS (Folhas de Estilos em Cascata). Também poderá usar imagens se você hospedá-las em um ponto de extremidade Web disponível publicamente. Para adicionar uma imagem, insira o URL da imagem no atributo **src** da tag **&lt;img&gt;** em HTML.

> [!NOTE]
> Os clientes de email impõem limitações de estilo e layout que podem exigir ajustes no HTML e CSS que você usa para o corpo da mensagem. Recomendamos que você se familiarize com as práticas recomendadas para criar HTML que receberá suporte dos clientes de email mais conhecidos.

## <a name="add-placeholders-to-the-email-message-body"></a>Adicionar espaços reservados ao corpo da mensagem de email

Seu email pode conter espaços reservados que são substituídos por valores específicos do cliente e de transação, quando o email é gerado. Os espaços reservados estão sempre entre sinais de porcentagem (%) e inseridos diretamente no documento HTML.

Veja aqui um exemplo.

```html
<p>
    Hello %customername%,<br />
    Order number %salesid%, can be picked up from the <b>%pickupstorename%</b> store.
</p>
```

### <a name="order-placeholders-sales-order-level"></a>Espaços reservados de ordens (nível de ordem de venda)

Os espaços reservados a seguir recuperam e mostram dados definidos no nível de ordem de venda (em oposição ao nível de linha de venda).

| Nome do espaço reservado     | Finalidade                                                      |
| -------------------- | ------------------------------------------------------------ |
| `customername`         | O nome do cliente que fez a ordem.               |
| `customeraddress`      | O endereço do cliente.                                 |
| `customeremailaddress` | O endereço de email inserido pelo cliente na finalização da compra.     |
| `salesid`              | A ID de vendas da ordem.                                   |
| `orderconfirmationid`  | A ID do canal cruzado que foi gerada na criação da ordem.   |
| `channelid`            | A ID do canal de varejo ou online para o qual a ordem foi feita. |
| `deliveryname`         | O nome que é especificado para o endereço de entrega.         |
| `deliveryaddress`      | O endereço de entrega para ordens remetidas.                     |
| `deliverydate`         | A data de entrega.                                           |
| `shipdate`             | A data de remessa.                                               |
| `modeofdelivery`       | O modo de entrega da ordem.                              |
| `ordernetamount`       | O valor total da ordem, menos o imposto total.         |
| `discount`            | O total de descontos da ordem.                            |
| `charges`              | O total de encargos da ordem.                             |
| `tax`                  | O total de impostos da ordem.                                 |
| `total`                | O valor total da ordem.                              |
| `storename`            | O nome da loja em que foi feita a ordem.            |
| `storeaddress`         | O endereço da loja que fez a ordem.              |
| `storeopenfrom`        | O horário de abertura da loja que fez a ordem.         |
| `storeopento`          | O horário de fechamento da loja que fez a ordem.         |
| `pickupstorename`      | O nome da loja em que a ordem será retirada.\*   |
| `pickupstoreaddress`   | O endereço da loja em que a ordem será retirada.\* |
| `pickupopenstorefrom`  | O horário de abertura da loja em que a ordem será retirada.\* |
| `pickupopenstoreto`    | O horário de fechamento da loja em que a ordem será retirada.\* |
| `pickupchannelid`     | A ID de canal do armazenamento especificado para um modo de entrega de retirada.\* |
| `packingslipid`        | A ID da guia de remessa que foi gerada quando as linhas de uma ordem foram embaladas.\* |

\*Estes espaços reservados retornam dados somente quando são usados para o tipo de notificação **Ordem pronta para retirada**. 

### <a name="order-line-placeholders-sales-line-level"></a>Espaços reservados da linha de ordem (nível da linha de venda)

Os espaços reservados a seguir recuperam e mostram dados de produtos individuais (linhas) na ordem de venda.

| Nome do espaço reservado               | Finalidade |
|--------------------------------|-------------------|
| `productid`                      | <p>A ID do produto. Esta ID é responsável por grades.</p><p><strong>Observação:</strong> esse espaço reservado foi preterido em favor de `lineproductrecid`.</p> |
| `lineproductrecid`               | A ID do produto. Esta ID é responsável por grades. Ele identifica exclusivamente um item no nível da grade. |
| `lineitemid`                     | A ID do nível do produto. (Esta ID não é responsável por grades.) |
| `lineproductvariantid`           | A ID da grade de produto. |
| `lineproductname`                | O nome do produto. |
| `lineproductdescription`         | A descrição do produto. |
| `linequantity`                   | O número de unidades que foram solicitadas para a linha, mais a unidade de medida (por exemplo, **ea** ou **par**). |
| `lineunit`                       | A unidade de medida da linha. |
| `linequantity_withoutunit`       | O número de unidades que foram solicitadas para a linha, sem a unidade de medida. |
| `linequantitypicked`             | Quando o evento **PickOrder** é usado, o número de unidades que foram coletadas. Caso contrário, **0** (zero). |
| `linequantitypicked_withoutunit` | Quando o evento **PickOrder** é usado, o número de unidades que foram coletadas, sem a unidade de medida. Caso contrário, **0** (zero). |
| `linequantitypacked`             | Quando os eventos **PackOrder** e **Ordem pronta para retirada** são usados, o número de unidades que foram embaladas. Caso contrário, **0** (zero). |
| `linequantitypacked_withoutuom`  | Quando os eventos **PackOrder** e **Ordem pronta para retirada** são usados, o número de unidades que foram embaladas, sem a unidade de medida. Caso contrário, **0** (zero). |
| `linequantityshipped`            | Sempre **0**, exceto quando eventos específicos são usados, conforme descrito na linha seguinte. |
| `linequantityshipped_withoutuom` | Quando o evento **ShipOrder** é usado, o número de unidades que foram coletadas, sem a unidade de medida. Caso contrário, **0** (zero). |
| `lineprice`                      | O preço de uma única unidade. |
| `linenetamount`                  | O preço da linha depois do número de unidades e do desconto serem aplicados. |
| `linediscount`                   | O desconto de uma unidade individual. |
| `lineshipdate`                   | A data de remessa da linha. |
| `linedeliverydate`               | A data de entrega da linha. |
| `linedeliverymode`               | O modo de entrega da linha. |
| `linedeliveryaddress`            | O endereço de entrega da linha. |
| `linepickupdate`                 | A data de retirada especificada pelo cliente para ordens que usam um modo de entrega de retirada. |
| `linepickuptimeslot`             | O intervalo de tempo de retirada especificado pelo cliente para ordens que usam um modo de entrega de retirada. |
| `giftcardnumber`                 | O número do cartão-presente para produtos do tipo de cartão-presente. |
| `giftcardbalance`                | O saldo do cartão-presente para produtos do tipo de cartão-presente. |
| `giftcardmessage`                | A mensagem do cartão-presente para produtos do tipo de cartão-presente. |
| `giftcardpin`                    | O PIN do cartão-presente para produtos do tipo de cartão-presente. (Este espaço reservado é específico de cartões-presente externos.) |
| `giftcardexpiration`             | A data de vencimento do cartão-presente para produtos do tipo de cartão-presente. (Este espaço reservado é específico de cartões-presente externos.) |
| `giftcardrecipientname`          | O nome do destinatário do cartão-presente para produtos do tipo de cartão-presente. |
| `giftcardbuyername`              | O nome do comprador do cartão-presente para produtos do tipo de cartão-presente. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Formato dos espaços reservados da linha de ordem no corpo da mensagem de email

Quando você criar o HTML para as linhas de ordem individuais no corpo da mensagem de email, coloque o bloco de repetição de HTML e os espaços reservados para as linhas com os espaços reservados a seguir. Observe que os espaços reservados estão dentro das tags de comentário HTML.

```html
<!--%tablebegin.salesline%-->

(Insert the repeating block of HTML and placeholders for individual lines here.)

<!--%tableend.salesline%-->
```

Veja aqui um exemplo.

```HTML
<table>
    <tr>
        <td>Product name</td>
        <td>Quantity</td>
        <td>Price</td>
    </tr>
    <!--%tablebegin.salesline%-->
    <tr>
        <td>%lineproductname%</td>
        <td>%linequantity_withoutunit%</td>
        <td>%lineprice%</td>
    </tr>
    <!--%tableend.salesline%-->
</table>
```

## <a name="create-a-template-for-emailed-receipts"></a>Crie um modelo para recibos enviados por email

Os recibos podem ser enviados por email para clientes que fazem compras em um PDV (ponto de venda de varejo). Em geral, as etapas para a criação do modelo de recibo por email são as mesmas etapas para criar modelos para outros eventos transacionais. No entanto, são necessárias as seguintes alterações:

- O espaço reservado **%message%** é usado para inserir texto do recibo no email. Para garantir que o corpo do recibo seja processado corretamente, coloque o espaço reservado **%message%** entre as marcas HTML **&lt;pre&gt;** e **&lt;/pre&gt;**.
- O espaço reservado **%receiptid%** pode ser usado para mostrar um código QR ou código de barras que representa a ID do recibo. (Os códigos QR e os códigos de barras são gerados dinamicamente e servidos por um serviço terceirizado). Para obter mais informações sobre como mostrar um código QR ou código de barras em um recibo enviado por email, consulte [Adicionar um código QR ou código de barras a emails transacionais e de recebimento](add-qr-code-barcode-email.md).

## <a name="upload-the-email-html"></a>Carregar o HTML do email

Depois de criar e testar o HTML para o corpo da mensagem, ele deverá ser carregado para o Commerce headquarters. No momento, não é possível exportar o HTML do email. Portanto, você deve manter a cópia principal do seu HTML fora do Commerce headquarters.

Para carregar um HTML de modelo de email novo ou editado, siga estas etapas.

1. Em Commerce Headquarters, Acesse **Varejo e Comércio \> Configuração da sede \> Modelos de email da organização**.
1. Selecione a linha do idioma para o qual você deseja adicionar ou substituir o HTML. Outra opção é selecionar **Novo** para criar uma linha para um novo idioma.
1. Selecione **Editar**.
1. Na caixa de diálogo exibida, selecione **Navegar**. Navegue até o documento HTML a ser carregado, selecione-o e, depois, selecione **Abrir**.
1. Selecione **Carregar**.
1. Depois que o HTML do email aparecer na janela de visualização, selecione **OK**.
1. Verifique se a caixa de seleção **Tem corpo** está marcada para a linha.

Se você já configurou o Commerce headquarters para enviar emails, seus emails novos ou atualizados serão enviados para todos os clientes que executam uma transação que invoca o evento mapeado para o modelo.

Para obter mais informações sobre como configurar emails no Dynamics 365 Commerce, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md).

## <a name="additional-resources"></a>Recursos adicionais 

[Configurar perfil de notificação por email](email-notification-profiles.md)

[Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md)

[Configurar recebimentos de email](/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Enviar recibos por email do Modern POS ](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
