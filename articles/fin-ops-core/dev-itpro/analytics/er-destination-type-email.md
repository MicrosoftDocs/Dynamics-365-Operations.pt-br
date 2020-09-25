---
title: Tipo de destino de ER do email
description: Este tópico fornece informações sobre como configurar um destino de email para cada componente de PASTA ou ARQUIVO de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 72f67ad915ba2acc90ecb52bdb97e42504450a03
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745552"
---
# <a name="email-destination"></a>Destino de email

[!include [banner](../includes/banner.md)]

Você pode configurar um destino de email para cada componente de PASTA ou ARQUIVO de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída. Com base na configuração de destino, um documento gerado é entregue como um anexo de uma mensagem eletrônica.

Definir **Habilitado** para **Sim** para enviar um arquivo de saída por e-mail. Depois que essa opção é ativada, você pode especificar os destinatários do email, bem como editar o assunto e o corpo da mensagem de email. Você pode configurar textos constantes para o assunto e corpo de email, ou pode usar [fórmulas](er-formula-language.md) de ER para criar textos de email dinamicamente. 

Você pode configurar endereços de email para o ER de duas formas. A configuração pode ser concluída da mesma forma que o recurso Gerenciamento de impressão a conclui, ou você pode resolver um endereço de email usando uma referência direta à configuração de ER por meio de uma fórmula.

[![Habilitar destino de email](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>Tipos de endereço de email

Quando você seleciona **Editar** nos campos **Para** ou **Cc**, a caixa de diálogo **Email para** é exibida. Você pode selecionar o tipo de endereço de email para uso. Atualmente, são aceitos os tipos de email **Email de configuração** e **Gerenciamento de impressão**.

[![Selecionar tipo de email](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management"></a>Gerenciamento de impressão

Se selecionar o tipo de email **Gerenciamento de impressão**, você poderá inserir os endereços de email fixos no campo **Para**. 

[![Configurar endereços de email fixos](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)

Para usar os endereços de e-mail não fixos, você deve selecionar o tipo de origem de e-mails para um destino de arquivo. Os valores a seguir são suportados: **Cliente**, **Fornecedor**, **Cliente potencial**, **Contato**, **Concorrente**, **Trabalhador**, **Candidato**, **Fornecedor potencial** e **Fornecedor não permitido**. Após selecionar um tipo de origem de email, use o botão ao lado do campo **Conta de origem do email** para abrir o formulário **Designer de fórmulas**. Você pode usar este formulário para anexar uma fórmula que retorne, no tempo de execução, a **conta do participante** do tipo de origem selecionado no documento processado para o destino do email.

[![Configurar conta de origem de email](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)

Fórmulas são específicas à configuração de ER. Em **Fórmula**, digite uma referência específica a um tipo da parte do cliente ou fornecedor. Em vez de digitar, você pode encontrar um nó da fonte de dados que represente a conta de cliente ou fornecedor e selecionar **Adicionar fonte de dados** para atualizar a fórmula. Por exemplo, se você usar a configuração **Transferência de Crédito ISO 20022**, o nó que representa uma conta de fornecedor será `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

Se você inserir um valor de sequência de caracteres, como `"DE-001"`, e salvar uma fórmula, um email será enviado à pessoa de contato do fornecedor, **DE-001**.


[![Página Designer de fórmula de ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)

[![Configurar conta de atributos de origem de email](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)



### <a name="configuration-email"></a>Email de configuração

Use esse tipo de email se a configuração que você usar tiver um nó nas fontes de dados que retorna um **endereço de email**. Você pode usar fontes de dados e as funções no designer de fórmulas para obter um endereço de email corretamente formatado. Por exemplo, se você usar a configuração **Transferência de Crédito ISO 20022**, o nó que representa um endereço de email da pessoa de contato de um fornecedor será `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Configurar origem do endereço de email](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)
- [Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)
- [Designer de fórmulas no relatório eletrônico (ER)](general-electronic-reporting-formula-designer.md)
