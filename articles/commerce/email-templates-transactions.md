---
title: Criar modelos de email para eventos transacionais
description: Este tópico descreve como criar, carregar e configurar modelos de email para eventos transacionais no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 05/28/2021
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
ms.openlocfilehash: 2da1044cd332d841a8c18f7139d0d8c09bad95f446494034060e59416b4018b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718698"
---
# <a name="create-email-templates-for-transactional-events"></a>Criar modelos de email para eventos transacionais

[!include [banner](includes/banner.md)]

Este tópico descreve como criar, carregar e configurar modelos de email para eventos transacionais no Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce fornece uma solução pronta para enviar emails que alertam clientes sobre eventos transacionais (por exemplo, quando uma ordem é feita, uma ordem está pronta para ser retirada ou uma ordem é enviada). Este tópico descreve as etapas para criar, carregar e configurar os modelos de email usados para enviar emails transacionais.

## <a name="create-an-email-template"></a>Criar um modelo de email

Para poder mapear um evento transacional específico para um modelo de email, você precisa criar o modelo.

Para criar um modelo de email, siga estas etapas.

1. No Commerce Headquarters, acesse **Varejo e Comércio \> Configuração do Headquarters \> Modelos de email da organização** ou **Administração da organização \> Configuração \> Modelos de email da organização**.
1. Selecione **Novo**.
1. Em **Geral**, defina os seguintes campos:

    - **ID de email** – a ID de email é o identificador exclusivo de um modelo e o valor mostrado quando você seleciona um modelo a ser mapeado para um evento.
    - **Descrição do email** – você pode usar este campo opcional para fornecer uma descrição do modelo. O valor inserido aparece somente em Commerce headquarters.
    - **Nome do remetente** – o nome inserido aparece no campo "de" da maioria dos clientes de email.
    - **Email do remetente** – insira o endereço de email que deve ser usado para emails enviados usando esse modelo.
    - **Código do idioma padrão** – este campo especifica a versão localizada do email enviado por padrão, caso nenhum idioma seja fornecido pelo canal que invoca esse modelo.

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

| Nome do espaço reservado     | Valor do espaço reservado                                            |
| -------------------- | ------------------------------------------------------------ |
| customername         | O nome do cliente que fez a ordem.               |
| customeraddress      | O endereço do cliente.                                 |
| customeremailaddress | O endereço de email inserido pelo cliente na finalização da compra.     |
| salesid              | A ID de vendas da ordem.                                   |
| orderconfirmationid  | A ID do canal cruzado que foi gerada na criação da ordem. |
| channelid            | A ID do canal de varejo ou online para o qual a ordem foi feita. |
| deliveryname         | O nome que é especificado para o endereço de entrega.        |
| deliveryaddress      | O endereço de entrega para ordens remetidas.                     |
| deliverydate         | A data de entrega.                                           |
| shipdate             | A data de remessa.                                               |
| modeofdelivery       | O modo de entrega da ordem.                              |
| ordernetamount       | O valor total da ordem, menos o imposto total.         |
| desconto             | O total de descontos da ordem.                            |
| charges              | O total de encargos da ordem.                             |
| imposto                  | O total de impostos da ordem.                                 |
| total                | O valor total da ordem.                              |
| storename            | O nome da loja em que foi feita a ordem.            |
| storeaddress         | O endereço da loja que fez a ordem.              |
| storeopenfrom        | O horário de abertura da loja que fez a ordem.         |
| storeopento          | O horário de fechamento da loja que fez a ordem.         |
| pickupstorename      | O nome da loja em que a ordem será retirada.\* |
| pickupstoreaddress   | O endereço da loja em que a ordem será retirada.\* |
| pickupopenstorefrom  | O horário de abertura da loja em que a ordem será retirada.\* |
| pickupopenstoreto    | O horário de fechamento da loja em que a ordem será retirada.\* |
| pickupchannelid      | A ID de canal do armazenamento especificado para um modo de entrega de retirada.\* |
| packingslipid        | A ID da guia de remessa que foi gerada quando as linhas de uma ordem foram embaladas.\* |

\*Estes espaços reservados retornam dados somente quando são usados para o tipo de notificação **Ordem pronta para retirada**. 

### <a name="order-line-placeholders-sales-line-level"></a>Espaços reservados da linha de ordem (nível da linha de venda)

Os espaços reservados a seguir recuperam e mostram dados de produtos individuais (linhas) na ordem de venda.

| Nome do espaço reservado               | Valor do espaço reservado |
|--------------------------------|-------------------|
| productid                      | <p>A ID do produto. Esta ID é responsável por grades.</p><p><strong>Observação:</strong> Este espaço reservado foi preterido por **lineproductrecid**.</p> |
| lineproductrecid               | A ID do produto. Esta ID é responsável por grades. Ele identifica exclusivamente um item no nível da grade. |
| lineitemid                     | A ID do nível do produto. (Esta ID não é responsável por grades.) |
| lineproductvariantid           | A ID da grade de produto. |
| lineproductname                | O nome do produto. |
| lineproductdescription         | A descrição do produto. |
| linequantity                   | O número de unidades que foram solicitadas para a linha, mais a unidade de medida (por exemplo, **ea** ou **par**). |
| lineunit                       | A unidade de medida da linha. |
| linequantity_withoutunit       | O número de unidades que foram solicitadas para a linha, sem a unidade de medida. |
| linequantitypicked             | Quando o evento **PickOrder** é usado, o número de unidades que foram coletadas. Caso contrário, **0** (zero). |
| linequantitypicked_withoutunit | Quando o evento **PickOrder** é usado, o número de unidades que foram coletadas, sem a unidade de medida. Caso contrário, **0** (zero). |
| linequantitypacked             | Quando os eventos **PackOrder** e **Ordem pronta para retirada** são usados, o número de unidades que foram embaladas. Caso contrário, **0** (zero). |
| linequantitypacked_withoutuom  | Quando os eventos **PackOrder** e **Ordem pronta para retirada** são usados, o número de unidades que foram embaladas, sem a unidade de medida. Caso contrário, **0** (zero). |
| linequantityshipped            | Sempre **0**, exceto quando eventos específicos são usados, conforme descrito na linha seguinte. |
| linequantityshipped_withoutuom | Quando o evento **ShipOrder** é usado, o número de unidades que foram coletadas, sem a unidade de medida. Caso contrário, **0** (zero). |
| lineprice                      | O preço de uma única unidade. |
| linenetamount                  | O preço da linha depois do número de unidades e do desconto serem aplicados. |
| linediscount                   | O desconto de uma unidade individual. |
| lineshipdate                   | A data de remessa da linha. |
| linedeliverydate               | A data de entrega da linha. |
| linedeliverymode               | O modo de entrega da linha. |
| linedeliveryaddress            | O endereço de entrega da linha. |
| linepickupdate                 | A data de retirada especificada pelo cliente para ordens que usam um modo de entrega de retirada. |
| linepickuptimeslot             | O intervalo de tempo de retirada especificado pelo cliente para ordens que usam um modo de entrega de retirada. |
| giftcardnumber                 | O número do cartão-presente para produtos do tipo de cartão-presente. |
| giftcardbalance                | O saldo do cartão-presente para produtos do tipo de cartão-presente. |
| giftcardmessage                | A mensagem do cartão-presente para produtos do tipo de cartão-presente. |
| giftcardpin                    | O PIN (número de identificação pessoal) do cartão-presente para produtos do tipo de cartão-presente. (Este espaço reservado é específico de cartões-presente externos.) |
| giftcardexpiration             | A data de vencimento do cartão-presente para produtos do tipo de cartão-presente. (Este espaço reservado é específico de cartões-presente externos.) |
| giftcardrecipientname          | O nome do destinatário do cartão-presente para produtos do tipo de cartão-presente. |
| giftcardbuyername              | O nome do comprador do cartão-presente para produtos do tipo de cartão-presente. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Formato dos espaços reservados da linha de ordem no corpo da mensagem de email

Quando você criar o HTML para as linhas de ordem individuais no corpo da mensagem de email, coloque o bloco de repetição de HTML e espaços reservados para as linhas com os espaços reservados a seguir que são colocados dentro de tags de comentários HTML.

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

- O texto do recibo é inserido no email usando o espaço reservado **%message%**. Para garantir que o corpo do recibo seja processado corretamente, coloque o espaço reservado **%message%** entre as marcas HTML **&lt;pre&gt;** e **&lt;/pre&gt;**.
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
