---
title: "Grupos de objetos de serviço"
description: "Grupos de objetos são úteis para classificar e filtrar os dados sobre objetos para relatórios e estatísticas."
author: YuyuScheller
manager: AnnBe
ms.date: 05/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2ab3ed8a8f36f980473b17b5dfed8cb3d0054253
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="service-object-groups"></a>Grupos de objetos de serviço 

[!include [banner](../includes/banner.md)]

Grupos de objetos são úteis para classificar e filtrar os dados sobre objetos para relatórios e estatísticas. Por exemplo, você pode agrupar objetos por localização geográfica ou tipo.

## <a name="group-by-geographical-location"></a>Agrupar por localização geográfica

Você pode usar este método de agrupamento para mostrar onde estão localizados os vários objetos diferentes para os quais sua empresa presta serviços. Agrupar objetos por localização geográfica também poderá ser útil se, por exemplo, for necessário identificar os objetos para os quais sua empresa presta serviços em um país/região específico.

## <a name="example"></a>exemplo

Um cliente da Bélgica liga para o seu centro de serviço e deseja criar uma contrato de serviço para um objeto, ABC. Você associou um grupo de objetos para localização geográfica, Bélgica, a todos os objetos atendidos na Bélgica. Usando esse grupo como um filtro, você pode pesquisar rapidamente e consultar se já existe um registros para ABC no programa ou se é necessário configurar um novo objeto. 

## <a name="group-by-type"></a>Agrupar por tipo

Você pode usar este método de agrupamento para mostrar os tipos de objetos que sua empresa presta serviços. Agrupar objetos por tipo também pode ser útil se, por exemplo, você deseja criar um novo objeto com base em objetos semelhantes que já existam no programa.

## <a name="example"></a>exemplo

Um cliente liga e deseja definir um contrato de serviço para uma máquina de ar-condicionado, HIJ. Você ainda não tem um registro para este computador. No entanto, você configurou um grupo de objetos intitulado Ar-condicionados e associou esse grupo a todos os objetos de ar-condicionado. Portanto, é possível pesquisar rapidamente e identificar todas as outras máquinas de ar-condicionado e usar as informações do modelo desses objetos para criar linhas de contrato de serviço para HIJ. Ao usar grupos de objetos dessa maneira, você pode configurar rapidamente novos objetos e determinar as tarefas de serviço que devem ser realizadas neles. 

## <a name="create-service-object-groups"></a>Criar grupos de objetos de serviço

Crie grupos aos quais você pode atribuir objetos de serviço. Os objetos de serviço são itens de estoque e outros produtos para os quais os serviços são executados. Ao agrupar objetos de serviço, você pode criar relatórios de objetos de serviço semelhantes e relacionados. Por exemplo, um grupo de objetos de serviço pode consistir em dois objetos de serviço: um objeto de serviço é um kit, e o segundo objeto de serviço é o serviço para instalar o kit.

Para criar grupos de objetos de serviço, siga estas etapas:

1. Clique em **Gerenciamento de serviços > Configuração > Objetos de serviço > Grupos de objetos de serviço**.

2. Clique em **Novo** para criar um novo grupo de objetos de serviço.

3. Insira um nome exclusivo para o grupo de objetos de serviço e, opcionalmente, uma descrição.

Você pode atribuir objetos de serviço ao grupo usando o formulário **Objetos de serviço**. 

## <a name="see-also"></a>Consulte também

[Criar objetos de serviço](create-service-objects.md)



