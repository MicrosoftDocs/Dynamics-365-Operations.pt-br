---
title: Criar estilo para a interface de execução de piso de produção
description: O tópico explica como configurar controles de formulário para que os estilos padrão da execução de piso de produção sejam aplicados a eles.
author: johanhoffmann
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 32e49458f6ea7c484bc4200e414d930381b31891
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651925"
---
# <a name="style-the-production-floor-execution-interface"></a>Criar estilo para a interface de execução de piso de produção

[!include [banner](../includes/banner.md)]

O tópico explica como configurar controles de formulário para que os estilos padrão da execução de piso de produção sejam aplicados a eles.

## <a name="forms-and-dialogs"></a>Formulários e caixas de diálogo

Os estilos podem ser aplicados a um formulário ou caixa de diálogo somente se os seguintes requisitos forem atendidos:

- Se o formulário tiver que se assemelhar ao formulário de progresso do relatório existente, o nome do formulário ou da caixa de diálogo deverá começar com **JmgProductionFloorExecutionCustomInputDialog**.
- O formulário ou caixa de diálogo pode conter uma parte do formulário de detalhes. Para aplicar estilos a ele, o nome da parte do formulário de detalhes deve começar com **JmgProductionFloorExecutionCustomDetailsDialog**.
- Se o formulário ou caixa de diálogo tiver que ter uma exibição simples, o nome da exibição simples deverá começar com **JmgProductionFloorExecutionCustomDialog**. Exemplos de formulários que têm uma exibição simples incluem o formulário de início e o formulário de atividades indiretas.
- Todos os controles da caixa de diálogo devem ser configurados como descrito neste tópico.

> [!IMPORTANT]
> Os recursos mencionados nos dois primeiros marcadores desta lista exigem o Supply Chain Management versão 10.0.19 ou posterior.

Os estilos podem ser aplicados ao botão **OK** em uma caixa de diálogo somente se os seguintes requisitos forem atendidos:

- O botão está contido em um grupo de formulários.
- O nome do grupo começa com **OkButtonGroup**.

Os estilos podem ser aplicados ao botão **Cancelar** em uma caixa de diálogo somente se os seguintes requisitos forem atendidos:

- O botão está contido em um grupo de formulários.
- O nome do grupo começa com **CancelButtonGroup**.

## <a name="grid"></a>Grade

Os estilos são aplicados automaticamente. Nenhuma configuração específica é necessária.

## <a name="card-view"></a>Exibição de cartão

Os estilos podem ser aplicados aos controles de exibição de cartão somente se os seguintes requisitos forem atendidos:

- Cada exibição de cartão está contida em um grupo de formulários.
- O nome do grupo começa com **CardGroup** (por exemplo, **CardGroupJobsView**).

A ilustração a seguir mostra uma exibição de cartão que não tem controles.

![Exibição de cartão sem elementos.](media/pfe-styles-empty-card.png)

As ilustrações a seguir mostram exibições de cartão que têm controles.

![Cartão com elementos que mostram Hz.](media/pfe-styles-elements.png)

![Cartão com elementos para uma solicitação de manutenção.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Cartão de visita

Os estilos podem ser aplicados aos controles de cartão de visita somente se os seguintes requisitos forem atendidos:

- Cada cartão de visita está contido em um grupo de formulários.
- O nome do grupo começa com **BusinessCardGroup** (por exemplo, **BusinessCardGroupJobsList**).

Defina as seguintes propriedades no cartão de visita:

- **Estilo**: **lista**
- **Estilo estendido**: **cardList**
- **Seleção Múltipla**: **Não**
- **Mostrar Rótulos de Coluna**: **Não**

![Cartão de visita.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Botão de opção

Os estilos podem ser aplicados aos botões de opção somente se os seguintes requisitos forem atendidos:

- Cada botão de opção está contido em um grupo de formulários.
- O nome do grupo começa com **RadioTextBelow** ou **RadioTextRight**, dependendo de onde você deseja que o texto apareça.

Defina as seguintes propriedades no botão de opção:

- **Botão de alternância**: **Verificar**
- **Valor de alternância**: **Ativado** se o botão de opção tiver que ser selecionado; caso contrário, **Desativado**

A ilustração a seguir mostra um exemplo no qual o texto é exibido abaixo dos botões de opção.

![Botões de opção com texto abaixo.](media/pfe-styles-radio-text-below.png)

A ilustração a seguir mostra um exemplo no qual o texto é exibido à direita dos botões de opção.

![Botões de opção com texto à direita.](media/pfe-styles-radio-text-right.png)

### <a name="radio-buttons-in-internet-explorer"></a>Botões de opção no Internet Explorer

Não há suporte para estilos de botões de opção no Internet Explorer. A ilustração a seguir mostra a aparência dos botões de opção no Internet Explorer.

![Botões de opção no Internet Explorer.](media/pfe-styles-browser.png)

## <a name="buttons"></a>Botões

Os estilos podem ser aplicados aos botões somente se os seguintes requisitos forem atendidos:

- Cada grupo de botões está contido em um grupo de formulários. Todos os botões do grupo terão o mesmo estilo.
- Não há requisitos para o nome do grupo.

Defina as seguintes propriedades nos botões:

- **Exibição do Botão**: **TextWithImageLeft**.
- **Imagem Normal**: esta propriedade não pode ficar em branco. Por exemplo, use **CoffeeScript**.
- **Texto**: esta propriedade não pode ficar em branco. Por exemplo, use **Iniciar Intervalo**.
- **Largura**: **Automático**.
- **Altura**: **Automático**.

### <a name="primary-button"></a>Botão principal

Os estilos podem ser aplicados a um botão principal somente se os seguintes requisitos forem atendidos:

- O botão está contido em um grupo de formulários.
- O nome do grupo começa com **DefaultButtonGroup** ou **PrimaryButtonGroup** (por exemplo, **DefaultButtonGroup10**).

![Botão principal.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Botão secundário

Os estilos podem ser aplicados a um botão secundário somente se os seguintes requisitos forem atendidos:

- O botão está contido em um grupo de formulários.
- O grupo é denominado **Painel direito** ou o nome do grupo começa com **SecondaryButtonGroup**.

![Botão secundário.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Botão de terceiro grupo

Os estilos podem ser aplicados a um botão de terceiro grupo somente se os seguintes requisitos forem atendidos:

- O botão está contido em um grupo de formulários.
- O grupo é denominado **Painel esquerdo** ou o nome do grupo começa com **ThirdButtonGroup**.

![Botão de terceiro grupo.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Botão de quarto grupo

Os estilos podem ser aplicados a um botão de quarto grupo somente se os seguintes requisitos forem atendidos:

- O botão está contido em um grupo de formulários.
- O nome do grupo começa com **FourthButtonGroup**.

Defina as seguintes propriedades no botão:

- **Exibição do Botão**: **TextOnly**.
- **Imagem Normal**: esta propriedade deve ficar em branco.
- **Texto**: esta propriedade não pode ficar em branco. Por exemplo, use **Exibir** ou **Editar**.
- **Largura**: **Automático**.
- **Altura**: **Automático**.

![Botão de quarto grupo.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Botão plano

Os estilos podem ser aplicados a um botão plano somente se os seguintes requisitos forem atendidos:

- O botão está contido em um grupo de formulários.
- O nome do grupo começa com **FlatButtonGroup**.

Defina as seguintes propriedades no botão:

- **Exibição do Botão**: **ImageOnly**.
- **Imagem Normal**: esta propriedade não pode ficar em branco. Por exemplo, use **CoffeeScript**.
- **Texto**: esta propriedade deve ficar em branco.
- **Largura**: **Automático**.
- **Altura**: **Automático**.

![Botão plano.](media/pfe-styles-flat-button.png)

## <a name="combo-box"></a>Caixa de combinação

Uma caixa de combinação é uma combinação de três controles: um controle de entrada, um botão que limpa o controle de entrada e um botão que executa uma pesquisa.

Os estilos podem ser aplicados a uma caixa de combinação somente se os seguintes requisitos forem atendidos:

- A caixa de combinação está contida em um grupo de formulários.
- O nome do grupo começa com **Combobox**.
- Dentro do grupo, o primeiro controle é um controle **AxFormStringControl**. Esse controle mostra o valor atual e é onde o usuário insere o valor necessário.
- O segundo controle é um controle **CommonButton**, e seu nome começa com **ClearButton**. Esse botão deve conter um código que use a propriedade **habilitar** para mostrar ou ocultar o botão. Por exemplo, para mostrar ou ocultar o botão **Limpar** enquanto o usuário digita informações no controle de entrada, você pode usar o código a seguir.

    ```xpp
    public void textChange()
    {
        super();
        ClearButtonSerial.enabled(this.text()? true : false);
    }
    ```

    Você deve ter um método no qual os dados sejam definidos no controle de entrada. Habilite o botão **Limpar** nesse método. Veja aqui um exemplo.

    ```xpp
    public void setSerialId(str _serialId)
    {
        JmgTmpJobBundleProdFeedback.InventSerial = _serialId;
        ClearButtonSerial.enabled(_serialId? true : false);

        if (_serialId)
        {
            this.addSerialNumber();
        }
    }
    ```

    Use o código a seguir para o método **clicked** do botão **Limpar**.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    Defina o valor do controle de entrada, **AxFormStringControl**, quando o formulário for inicializado usando o método **init**. Se o valor não estiver em branco, habilite o botão **Limpar**. Se o valor estiver em branco, desabilite o botão **Limpar**.

- O terceiro controle é um controle **CommonButton**, e seu nome começa com **SearchButton**.

A ilustração a seguir mostra dois controles de caixa de combinação. A caixa de combinação à esquerda tem uma caixa de texto vazia e o botão **Limpar** está desabilitado. A caixa de combinação à direita tem texto na caixa de texto e o botão **Limpar** está habilitado.

![Caixas de combinação com e sem um botão Limpar.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Filtro rápido

O controle de filtro rápido adiciona um campo de pesquisa à página. Você pode aplicar estilos a um filtro rápido desde que os seguintes requisitos sejam atendidos:

- O filtro rápido está contido em um grupo de formulários.
- O nome do grupo começa com **SearchInputGroup**.
- Dentro do grupo, o primeiro controle é um controle **QuickFilter**. (É aqui que o usuário insere a cadeia de caracteres de pesquisa.)
- O segundo controle é um **FormStaticTextControl** com o nome **NumberOfResults**. (É opcional e mostra o número de itens encontrados, se incluído.)
- O terceiro controle é um controle **CommonButton** com um nome que começa com **ClearButton**.

A ilustração a seguir mostra dois controles de filtro rápido. O filtro rápido à esquerda tem um filtro rápido vazio e o número de resultados não é visível. O filtro rápido à direita contém uma cadeia de caracteres de pesquisa e mostra o número de resultados.

![Exemplos de um controle de filtro rápido com e sem uma cadeia de caracteres de pesquisa.](media/pfe-styles-quick-filter.png "Exemplos de um controle de filtro rápido com e sem uma cadeia de caracteres de pesquisa")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
