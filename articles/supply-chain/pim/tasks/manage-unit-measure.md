---
title: Gerenciar unidades de medida
description: Este tópico descreve como definir uma unidade de medida, fornecer traduções para a unidade e sua descrição, e definir regras de conversão para unidades relacionadas.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d251f90675188426e74b8cbe672856eb4c9ecb8a391f54e735ba19b91b7e3f4a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746930"
---
# <a name="manage-units-of-measure"></a>Gerenciar unidades de medida

[!include [banner](../../includes/banner.md)]

Este tópico descreve como definir uma unidade de medida, fornecer traduções para a unidade e sua descrição, e definir regras de conversão para unidades relacionadas.

## <a name="open-the-units-page"></a>Abra a página Unidades

Para criar e trabalhar com as unidades de medida disponíveis no sistema, acesse **Administração da organização \> Configuração \> Unidades \> Unidades**.

As demais seções deste tópico descrevem o que você pode fazer na página **Unidades**.

## <a name="create-standard-units-and-conversions"></a>Criar unidades e conversões padrão

Se o sistema ainda não incluir as unidades de medida mais usadas para o sistema métrico e/ou o USCS (sistema de unidades de medidas dos EUA), o assistente de configuração da unidade poderá ajudá-lo a iniciar rapidamente as definições e conversões de unidades básicas. Para concluir o assistente, selecione **Assistente de criação de unidade** no Painel de Ações e siga as instruções na tela.

## <a name="create-or-edit-a-unit-of-measure"></a>Criar ou editar uma unidade de medida

Para criar ou editar uma unidade de medida, siga estas etapas.

1. Siga uma destas etapas:

    - Para editar uma unidade existente, selecione-a no painel de lista.
    - Para criar uma nova unidade, selecione **Novo** no Painel de Ações.

1. No cabeçalho do registro, defina os seguintes campos:

    - **Unidade** – insira a ID ou o símbolo a ser usado para fazer referência à unidade no idioma do sistema. Essa ID ou símbolo é geralmente uma abreviação comum da unidade, como *ea* para cada ou *cm* para centímetro.
    - **Descrição** – insira um nome descritivo para a unidade no idioma do sistema. Esse nome costuma ser o nome completo da unidade, como *Cada* ou *Centímetro*.

1. Na Guia Rápida **Geral**, defina os seguintes campos:<!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - **Classe de unidade** – selecione a propriedade que a unidade mede (como comprimento, área, massa ou quantidade).
    - **Sistema de unidades** – selecione o sistema de medição ao qual a unidade pertence (*Unidades métricas* ou *Unidades personalizadas dos Estados Unidos*).
    - **Unidade base** – defina esta opção como *Sim* para usar a unidade atual como a unidade base da sua classe de unidade. Nesse caso, você só precisa especificar o fator de conversão entre a unidade base e cada unidade adicional na classe de unidade. O sistema pode converter entre todas as unidades dessa classe de unidade. Portanto, é mais fácil configurar conversões.

        Por exemplo, se galão for a unidade base para a classe da unidade *Volume*, você só precisará configurar fatores de conversão de quarto para galão e de litro para galão. O sistema pode, então, ser convertido de quarto para litro.

        Só é possível ter uma unidade base por classe de unidade.

    - **Unidade do sistema** – defina esta opção como *Sim* para usar a unidade atual como a unidade presumida de todas as medidas na classe de unidade. Por exemplo, se um campo usado para inserir uma quantidade não permitir que uma unidade seja especificada (ou se o usuário não selecionar uma unidade), o sistema usará a unidade definida como a unidade do sistema para a classe de unidade *Quantidade*. Só é possível ter uma unidade de sistema por classe de unidade.
    - **Precisão decimal** – especifique o número de casas decimais para arredondamento de valores especificados para a unidade atual ou convertidas nela.

1. No Painel de ações, selecione **Salvar**.

## <a name="define-unit-translations"></a>Definir traduções de unidades

Para definir traduções para a ID ou o símbolo e a descrição de uma unidade de medida, siga estas etapas.

1. Crie ou selecione a unidade para a qual traduções serão criadas.
1. No Painel de Ações, selecione **Textos de unidade**.

    A página **Textos de unidade** é exibida. Use esta página para definir traduções para a ID ou o símbolo da unidade selecionada. Essas traduções podem ser usadas em documentos externos em idiomas específicos do cliente ou do fornecedor.

1. No Painel de Ações, selecione **Novo**.
1. No campo **Idioma**, selecione o idioma para o qual a ID de unidade ou o símbolo será traduzido.
1. No campo **Texto**, insira a tradução da ID da unidade ou o símbolo no idioma selecionado.
1. No Painel de ações, selecione **Salvar**.
1. Feche a página.
1. No **Painel de Ações**, selecione **Descrições da unidade traduzida**.

    A página **Descrições da unidade traduzida** aparece. Use esta página para definir descrições específicas do idioma para a unidade selecionada.

1. No Painel de Ações, selecione **Novo**.
1. No campo **Idioma**, selecione o idioma para o qual a descrição de unidade será traduzida.
1. No campo **Descrição**, insira a tradução da descrição da unidade no idioma selecionado.
1. No Painel de ações, selecione **Salvar**.
1. Feche a página.

## <a name="define-unit-conversion-rules"></a>Definir regras de conversão de unidades

Para definir regras para conversões entre unidades de medida, siga estas etapas.

1. Crie ou selecione a unidade para a qual regras de conversão serão definidas.
1. No Painel de Ações, selecione **Conversões de unidade**.

    A página **Conversões de unidade** aparece. Use esta página para definir regras de conversão da unidade selecionada de e para outras unidades na classe de unidade.

1. Selecione uma das seguintes guias, de acordo com o tipo de conversão a ser configurada:

    - **Conversões padrão** – configure regras de conversão padrão para todos os produtos.
    - **Conversões na mesma classe** – configure regras de conversão específicas de produtos para unidades na mesma classe de unidade.
    - **Conversões entre classes** – configure regras de conversão específicas de produtos para unidades entre classes de unidade.

1. Siga uma destas etapas:

    - Para criar uma nova conversão, selecione **Novo** no barra de ferramentas.
    - Para editar uma conversão existente, selecione a conversão na grade e, depois, selecione **Editar** na barra de ferramentas.

1. Na caixa de diálogo suspensa que aparecer, defina os seguintes campos:

    - **Produto** – selecione o produto específico ao qual a conversão se aplica. Este campo está disponível somente para conversões na mesma classe e entre classes.
    - **Layout da fórmula** – deixe este campo definido como *Simples* para especificar uma conversão simples que tenha um único fator. Defina-o como *Avançado* para configurar uma equação mais complexa. O formato das equações avançadas varia, dependendo da classe de unidade.
    - **Da unidade** – este campo mostra a unidade selecionada. Normalmente, você não deve alterar o valor. (Se você alterar o valor, deverá abrir a página **Conversões de unidade** da unidade selecionada para exibir a nova conversão após salvá-la.)
    - **Para unidade** – selecione a unidade a ser convertida.
    - **Arredondamento** – selecione como frações devem ser arredondadas, com base no valor **Precisão decimal** da unidade selecionada (*Para o mais próximo*, *Para cima* ou *Para baixo*).
    - **Fórmula de conversão** – use os campos restantes na parte superior da caixa de diálogo suspensa para especificar a fórmula para a conversão entre as duas unidades. Os campos disponíveis variam de acordo com a classe de unidade e o layout da fórmula selecionados.

1. Selecione **OK**.
1. Feche a página.

> [!TIP]
> Você também pode configurar conversões de unidades por grade de produto. Para obter mais informações, consulte [Conversão de unidade de medida por grade de produto](../uom-conversion-per-product-variant.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
