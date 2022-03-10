---
title: Configurar hierarquias da organização
description: Este tópico descreve como configurar hierarquias da organização no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ce0732f32a9a80fc5b0ede7ae9f1c1ab9a68a89b2fb0b1821cb5df123ca5ca4a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746007"
---
# <a name="set-up-organization-hierarchies"></a>Configurar hierarquias da organização

[!include [banner](includes/banner.md)]

Este tópico descreve como configurar hierarquias da organização no Microsoft Dynamics 365 Commerce.

Antes de criar canais, você precisa se certificar de configurar as hierarquias da organização.

Você pode usar as hierarquias da organização para exibir e fazer relatórios sobre a empresa de várias perspectivas. Por exemplo, você pode configurar uma hierarquia para relatórios de impostos, legais ou estatutários. Você pode configurar outra hierarquia para criar relatórios sobre informações financeiras que não são necessárias legalmente, mas que são usadas para fins de relatórios internos.

Antes de criar uma hierarquia da organização, você deve criar organizações. Para obter mais informações, consulte [Criar entidades legais](channels-legal-entities.md) ou [Criar unidades operacionais](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).


Para obter mais informações, consulte os tópicos a seguir.
- [Visão geral de organizações e hierarquias organizacionais](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [Planejar sua hierarquia da organização](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [​Criar uma hierarquia da organização​](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a>Criar uma hierarquia da organização

Para criar uma hierarquia organizacional, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Configuração de Canal \> Hierarquias da organização**.
1. No painel de ação, selecione **Novo**.
1. No campo **Nome**, insira um valor.
1. Na seção **Finalidade**, selecione **Atribuir finalidade**.
1. Na lista, localize e selecione o registro desejado. Selecione uma finalidade para atribuir a hierarquia da organização.
1. Na seção **Hierarquias atribuídas**, selecione **Adicionar**.
1. Na lista, marque a linha selecionada. Localizar a hierarquia que você acabou de criar.
1. Selecione **OK**.

A imagem a seguir mostra um exemplo de hierarquia organizacional criada para um conjunto de lojas "Adventure Works" fictícias.

![Exemplo de hierarquias organizacional.](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a>Adicionar organizações a uma hierarquia

Para adicionar organizações a uma hierarquia, siga estas etapas.

1. Na lista, localize e selecione o registro desejado. Selecionar sua hierarquia.
1. No painel de ação, selecione **Exibir**.
1. Adicione organizações, conforme necessário.
1. Para adicionar uma organização, selecione **Editar** e, depois, **Inserir**. Quando terminar de fazer alterações, você pode salvar um rascunho e publicar as alterações.

A imagem a seguir mostra uma entidade legal adicionada na raiz da hierarquia, com quatro centros de custo adicionados para os canais "Shopping", "Loja", "Online" e "Call Center". Vários canais online, de varejo e de call center podem ser adicionados a cada um deles.

![Exemplo de designer de hierarquia.](media/hierarchy-designer.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de organizações e hierarquias organizacionais](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planejar sua hierarquia da organização](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Criar entidades legais](channels-legal-entities.md)

[​Criar unidades operacionais](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
