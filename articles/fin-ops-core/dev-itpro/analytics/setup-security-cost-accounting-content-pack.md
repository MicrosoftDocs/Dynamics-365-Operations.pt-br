---
title: Configurar segurança do conteúdo da análise de contabilização de custos do Power BI
description: Este artigo explica como você pode propagar a segurança de nível de acesso em Contabilidade de custos para a segurança em nível de linha no Microsoft Power BI.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.openlocfilehash: 9f019bec9c28602e31b43a8b3ab820f4a3a31ee8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267922"
---
# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Configurar segurança do conteúdo da análise de contabilização de custos do Power BI

[!include [banner](../includes/banner.md)]

Este artigo explica como você pode propagar a segurança de nível de acesso em Contabilidade de custos para a segurança em nível de linha no Microsoft Power BI. Essa funcionalidade ajuda a garantir que os usuários vejam apenas os dados do Power BI aos quais eles têm acesso.

## <a name="overview"></a>Visão Geral

O conteúdo da **Análise de contabilidade de custo** do Microsoft Power BI usa a segurança a nível de linha do Power BI para limitar o acesso do usuário. A segurança é baseada na hierarquia organizacional de nível de acesso que é configurada nos parâmetros de contabilidade de custo previsto. Para obter mais informações sobre o conteúdo de **Análise de contabilidade de custo** do Power BI, consulte [Conteúdo de análise de contabilidade de custo do Power BI](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Instalação
Para propagar a segurança de nível de acesso ao Power BI, o proprietário do conteúdo do Power BI deve seguir estas etapas.

> [!NOTE]
> O usuário que publica conteúdo de **Análise da contabilização de custos** do Power BI se torna automaticamente o proprietário. Somente um proprietário pode configurar segurança no Power BI. Além disso, até que um proprietário adicione outros usuários no PowerBI.com, ninguém, exceto o proprietário, pode visualizar os dados no conteúdo de **Análise de contabilidade de custos** do Power BI.

1. Publicar o arquivo de definição no Power BI.
2. Entrar no PowerBI.com.
3. Localize o conjunto de dados para o conteúdo de **Análise de contabilidade de custos** do Power BI.
4. Abra a página de segurança.

    ![Abrindo a página de segurança.](./media/CA-picture-1.png)

5. A função **Controlador de objeto de custo** já está criada. Adicione outros membros que fazem parte da hierarquia organizacional do nível de acesso da contabilidade de custos.

    ![Adicionando membros.](./media/CA-picture-2.png)

Os usuários que forem adicionados à função **Controlador de objeto de custo** verão apenas os dados que eles estão autorizados a ver, de acordo com a definição na hierarquia organizacional de nível de acesso da contabilidade de custos.

> [!NOTE]
> A segurança em nível de linha aplica-se a blocos e relatórios que são incorporados pelo Power BI.

## <a name="updating-security"></a>Atualizando a segurança
Se forem feitas atualizações na segurança de nível de acesso na Contabilidade de custos e você desejar que o Power BI reflita essas atualizações, você deve atualizar o conteúdo de **Análise de contabilidade de custos** do Power BI. Depois de concluir a atualização de armazenamento de entidade, você deve atualizar os artefatos no PowerBI.com. Para obter mais informações sobre como fazer uma atualização de repositório de entidades, consulte [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md#update-entity-store). O proprietário do conteúdo de **Análise de contabilidade de custos** do Power BI também deve fazer uma atualização de armazenamento de entidade se novos usuários tiverem acesso concedido à hierarquia organizacional. Além disso, o proprietário deve adicionar os novos usuários à função **Controlador do objeto de custo** em PowerBI.com, de modo que a segurança em nível de linha seja aplicada a eles.

## <a name="disabling-security"></a>Desabilitando a segurança
Suponhamos que sua organização deseja restringir o acesso aos dados. Se, por algum motivo, os parâmetros de segurança estiverem desativados quando você executar Contabilidade de custos, o proprietário deverá adicionar usuários à função **Contador de custos** do Power BI. Se você alterar a segurança de um estado ativado para um estado desativado, é uma boa ideia remover usuários da função **Controlador de objetos de custo**. E vice-versa se você reativar a segurança. Os usuários podem pertencer a ambas funções. O acesso conjunto é a união de ambas as funções. No caso do conteúdo de **Análise de contabilidade de custos** do Power BI, os usuários que têm acesso conjunto têm acesso a dados sem restrições. Se o seu objetivo é aplicar acesso restrito, os usuários devem ser atribuídos somente à função **Controlador de objetos de custo**. Essas atualizações em nível de linha de segurança são efetivadas imediatamente. Os usuários devem afetados atualizam seus navegadores.

## <a name="additional-resources"></a>Recursos adicionais
Para saber mais sobre a segurança em nível de linha do Power BI, consulte [Gerenciar a segurança do seu modelo no Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-rls/#manage-security-on-your-model).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
