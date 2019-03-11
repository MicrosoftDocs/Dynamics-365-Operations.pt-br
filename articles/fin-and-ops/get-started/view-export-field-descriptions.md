---
title: Exibir e exportar descrições de campos
description: Este artigo descreve como exibir descrições dos campos e como usar a página de descrições de campo para exportação de descrições.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7be1495fc42b5f19884a7d9df747f6bec9b64680
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "359327"
---
# <a name="view-and-export-field-descriptions"></a>Exibir e exportar descrições de campos

[!include [banner](../includes/banner.md)]

Este artigo descreve como exibir descrições dos campos e como usar a página de descrições de campo para exportação de descrições.

O Microsoft Dynamics 365 for Finance and Operations tem descrições para alguns dos campos mais complexos. Essas descrições aparecem ao passar o mouse sobre um campo. Você também pode exibir e exportar descrições na página **Descrições de campo**.

Nem todas as páginas têm descrições de campo. Pretendemos fornecer descrições apenas dos campos mais complexos, e não daqueles cujo uso é evidente. Portanto, algumas páginas não têm todas as descrições de campo, algumas páginas possuem algumas descrições e algumas das páginas mais complexas, como muitas das páginas de parâmetros, há muitas descrições.

Se você tiver acesso ao ambiente de desenvolvimento do Finance and Operations, poderá adicionar suas próprias novas descrições aos campos e personalizar as descrições existentes. Por exemplo, você pode adicionar informações específicas da empresa para uma descrição de campo. Para mais informações, consulte [Personalizar campo de ajuda](../../dev-itpro/user-interface/customize-field-help.md).

## <a name="see-field-descriptions-in-the-user-interface"></a>Consulte as descrições na interface de usuário

Você pode exibir descrições de campo focalizando sobre um campo. Se nenhuma descrição estiver disponível, você verá o nome do campo quando passar o mouse no campo.

> [!NOTE]
> No Dynamics AX 7.0 (fevereiro de 2016), as descrições de campos podem ser exibidas somente na página **Descrições dos campos**.

A ilustração a seguir mostra a descrição do campo que aparece quando você passa o mouse no campo **Bloquear itens durante a contagem**.

[![Exemplo de uma descrição de campo](./media/field-description.png)](./media/field-description.png)

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a>Use a página Descrições de campo para exibir e exportar ajuda de campo

A página **Descrições de campos** permite exibir e exportar descrições de campos. Você pode ver, uma de cada vez, as descrições que estão disponíveis para uma página.

### <a name="view-the-descriptions-for-a-page"></a>Exibir as descrições de uma página

Para exibir as descrições para uma página, siga esta etapa.

- No campo **Selecionar uma página**, digite o nome da página. Como alternativa, clique na seta para abrir uma lista de todas as páginas e, em seguida, procure ou filtre a lista.

Você pode usar o nome da página que é exibido na interface do usuário (IU) (por exemplo: **Clientes**) ou o nome do código (nome da AOT) da página que está disponível quando você clica com botão direito do mouse nela (por exemplo: **CustTable**).

Para obter informações sobre as várias maneiras de filtrar a lista de páginas, consulte a seção "Procurando uma página" posteriormente neste artigo.

Se você definir a opção **Incluir campos sem uma descrição** para **Sim**, serão mostrados todos os campos da página, independentemente de terem ou não uma descrição.

### <a name="export-the-descriptions-for-a-page"></a>Exportar as descrições de uma página

Para exportar as descrições para uma página, siga estas etapas.

1. No campo **Selecionar uma página**, selecione uma página.
2. Clique no botão **Abrir no Microsoft Office** no canto superior direito e, depois, clique em **FieldDescriptionTmp**.

### <a name="searching-for-a-page"></a>Procurar uma página

Há várias maneiras de se pesquisar uma página no campo **Selecionar uma página**. Em muitos casos, você precisará clicar na seta no campo **Selecionar uma página** para abrir o menu suspenso e selecionar uma opção em uma lista filtrada de páginas.

- Digite uma parte do nome e, em seguida, abra a lista suspensa para selecionar uma lista filtrada de páginas.
- Abra o menu suspenso e clique no cabeçalho **Nome da página** na parte superior da lista ou no cabeçalho **Nome da AOT da página**. Isso abre uma caixa de diálogo na qual é possível usar opções de filtragem avançada, como **O nome da página começar com**.
- Digite o nome completo da página. Quando você usa esta opção, é aconselhável abrir o menu suspenso e verificar o que mais consta na lista, mesmo que as descrições dos campos sejam exibidas.

    - Se houver uma única correspondência exata ao nome, as descrições dos campos da página são exibidas.
    - Se houver mais de uma correspondência exata, não há descrições mostradas. Você deve abrir a lista suspensa e selecionar a página que você deseja.
    - Se o nome que você digitou é parte do nome de uma outra página, você verá as descrições da sua página. No entanto, se você abrir a lista suspensa, você verá outras páginas que contêm esse nome.

Por exemplo, nenhuma descrição é mostrada quando você digita **Contagem** no campo **Selecionar uma página**. Você abre a lista suspensa, e vê que há duas páginas que têm o nome de **Contagem** e diversas páginas que contêm a palavra "Contagem" no nome. Se você escolher a página que tem o mesmo nome da AOT **InventJournalCount**, as descrições dos campos dessa página serão mostradas. No entanto, ao abrir o menu suspenso novamente, você verá que a lista agora exibe todas as páginas que contêm “InventJournalCount” como parte do nome da página da AOT.

## <a name="troubleshooting"></a>Solução de problemas

Esta seção oferece informações para ajudá-lo a solucionar problemas que possam surgir durante o uso da página Descrições dos campos.

### <a name="i-cant-find-a-field-description"></a>Não consigo encontrar uma descrição de campo

Estamos no processo de adição de descrições aos campos mais complexos. Se você precisar de ajuda em relação a um determinado campo, avise-nos adicionando um comentário neste tópico.

### <a name="the-field-description-isnt-helpful"></a>A descrição do campo não é útil

Avise-nos adicionando um comentário a este tópico. Se possível, descreva as informações adicionais que você precisar.

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a>Não consigo localizar um campo na página de descrições de campo

Para mostrar todos os campos em uma página, defina a opção **Incluir campos sem uma descrição** como **Sim**. Clique no campo **Selecionar uma página** para verificar se você selecionou a página correta. Se o nome que você digitou é parte de outro nome de campo, talvez você tenha selecionado na página que tenha o nome mais longo.

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a>Não consigo localizar uma página na página Descrições de campo

Para obter informações sobre as várias maneiras de filtrar a lista de páginas, consulte a seção "Procurando uma página" anteriormente neste artigo. Se você digitar o nome exato da página, talvez as descrições dos campos não sejam exibidas se houver mais de uma página com o mesmo nome. Clique na seta no campo **Selecionar uma página** para abrir uma lista filtrada de páginas disponíveis.

## <a name="additional-resources"></a>Recursos adicionais

[Personalizar campo de ajuda](../../dev-itpro/user-interface/customize-field-help.md)
