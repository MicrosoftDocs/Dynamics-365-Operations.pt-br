---
title: Mover, substituir e instalar ativos
description: Este tópico explica como mover, substituir e instalar ativos no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 022ffc59b1b64913fedaf550f3fdb32141a94031
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020270"
---
# <a name="move-replace-and-install-assets"></a>Mover, substituir e instalar ativos

[!include [banner](../../includes/banner.md)]

 

Este tópico explica como mover, substituir e instalar ativos no Asset Management. Você pode criar ativos individuais sem relações com outros ativos, ou pode criar uma estrutura de ativos com um ativo pai (ativo de nível superior) e ativos secundários relacionados (subativos). No Asset Management, há três abordagens para mover e alterar o local de um ativo:

- **Mover** – mova um ativo para outra estrutura de ativos ou para outro local na mesma estrutura de ativos.
- **Substituir** – remova temporariamente um ativo de uma estrutura de ativos para que ele possa ser reparado ou reformado, e então adicione o ativo reformado de volta à estrutura de ativos. Como alternativa, substitua permanentemente um ativo usado por um novo ativo.
- **Instalar** – instale um ativo pai e quaisquer ativos secundários relacionados em um local funcional.

> [!NOTE]
> O ativo que você mover, substituir ou instalar pode estar relacionado a outro local funcional. Nesse caso, o ativo poderá usar dimensões financeiras do local funcional. Na página **Tipos de local funcional**, você configura a manipulação de dimensões financeiras em locais funcionais.

## <a name="move-asset"></a>Mover ativo

Use a função **Mover ativo** para mover um ativo para outra estrutura de ativos ou para outro local na mesma estrutura de ativos. Você também pode mover um ativo para fora da estrutura de ativos para que ele se torne um ativo autônomo sem nenhuma relação de estrutura.

> [!NOTE]
> Não use essa função se os ativos estiverem sendo reparados ou substituídos temporariamente. Em seu lugar, use a funcionalidade **Substituir ativo**, que será descrita posteriormente neste tópico.

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos** ou **Ativos ativos**.
2. Na lista, selecione o ativo a ser movido. Se o ativo tiver ativos secundários, você também os moverá.
3. Selecione **Mover ativo**.
4. Para mover o ativo para que se torne parte de uma estrutura de ativos, selecione o novo ativo pai no campo **Ativo pai**. Se você estiver movendo um ativo secundário, e se quiser torná-lo um ativo autônomo sem nenhuma relação de estrutura, deixe o campo **Ativo pai** em branco.
5. Por padrão, o campo **Efetivação** é definido como a data e hora atuais. Entretanto, você pode selecionar data e hora diferentes a partir das quais a movimentação do ativo será válida.
6. Selecione **OK**.

## <a name="replace-asset"></a>Substituir ativo

Use a função **Substituir ativo** em conjunto com reparos, restauração ou substituição permanente de um ativo esgotado por um novo ativo. Essa função é usada para substituir ativos secundários em uma estrutura de ativos. Para ativos pai (isto é, ativos que não têm um ativo pai), essa substituição é feita em um local funcional. Para obter mais informações sobre como substituir ativos pai em um local funcional, consulte [Instalar ativos em locais funcionais](../functional-locations/install-objects-on-functional-locations.md).

> [!NOTE]
> Se uma oficina estiver relacionada ao departamento de produção, você poderá criar locais funcionais como **Reparo**, **Sucata** e **Armazenamento** para controlar o reparo e a substituição de ativos.

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos** ou **Ativos ativos**.
2. Na lista, selecione o ativo secundário a ser substituído. Se o ativo tiver ativos secundários, você também os substituirá.
3. Selecione **Substituir ativo**.

    O campo **Alteração de estrutura** mostra a data e a hora mais recentes em que o ativo selecionado e os ativos secundários relacionados foram movidos na estrutura de ativos.

4. Na seção **Ativo selecionado**, no campo **Local funcional de destino**, selecione o local funcional para o qual o ativo será movido. Por exemplo, selecione o local **Reparo** ou **Sucata**.

    Na seção **Ativo pai**, o campo **Efetivação** mostra a data e a hora mais recentes em que o ativo pai e os ativos secundários relacionados foram instalados ou movidos no local funcional atual.

5. Na seção **Novo ativo**, no campo **Ativo**, selecione o ativo a ser inserido como substituto temporário ou permanente para o ativo selecionado. Esse ativo pode estar localizado em outro local funcional, como **Armazenamento**.
7. Na seção **Efetivo a partir de**, o campo **Efetivação** é definido como a data e hora atuais por padrão. Entretanto, você pode selecionar data e hora diferentes a partir das quais a substituição do ativo será válida.
8. Selecione **OK**.

## <a name="install-asset"></a>Instalar ativo

Use a função **Instalar ativo** para instalar uma estrutura de ativos em um local funcional.

> [!NOTE]
> Sempre selecione um ativo pai. O ativo pai e os ativos secundários relacionados serão movidos para o local funcional selecionado.

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos** ou **Ativos ativos**.
2. Na lista, selecione o ativo pai para instalar em outro local funcional.
3. Selecione **Instalar ativo**.

    A seção **Atributos** mostra os atributos de ativo configurados no ativo pai.

4. No campo **Local funcional**, selecione o novo local.
5. Por padrão, o campo **Efetivação** é definido como a data e hora atuais. Entretanto, você pode selecionar data e hora diferentes a partir das quais a instalação na estrutura de ativos será válida.
6. Selecione **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]