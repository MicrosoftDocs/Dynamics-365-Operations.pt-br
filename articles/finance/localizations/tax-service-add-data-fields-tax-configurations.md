---
title: Adicione campos de dados em configurações de imposto
description: Este tópico explica como personalizar as configurações de imposto adicionando campos de dados.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 197a2d1605dd39188841aba02a71d228c7138c54
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921180"
---
# <a name="add-data-fields-in-tax-configurations"></a><span data-ttu-id="ddf5d-103">Adicione campos de dados em configurações de imposto</span><span class="sxs-lookup"><span data-stu-id="ddf5d-103">Add data fields in tax configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ddf5d-104">Este tópico explica como personalizar configurações de imposto usando [campos de dados adicionados à integração de imposto](tax-service-add-data-fields-tax-integration-by-extension.md).</span><span class="sxs-lookup"><span data-stu-id="ddf5d-104">This topic explains how to customize tax configurations by using [data fields that are added in the tax integration](tax-service-add-data-fields-tax-integration-by-extension.md).</span></span>

## <a name="customize-the-tax-data-model"></a><span data-ttu-id="ddf5d-105">Personalizar o modelo de dados de imposto</span><span class="sxs-lookup"><span data-stu-id="ddf5d-105">Customize the tax data model</span></span>

1. <span data-ttu-id="ddf5d-106">No Microsoft Dynamics 365 Finance, acesse **Relatório Eletrônico** \> **Configurações de impostos**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-106">In Microsoft Dynamics 365 Finance, go to **Electronic Reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="ddf5d-107">Na árvore de configuração, selecione **Modelo de dados de imposto — Europa**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-107">In the configuration tree, select **Tax Data Model - Europe**.</span></span> <span data-ttu-id="ddf5d-108">Em seguida, no Painel de Ações, selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-108">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="ddf5d-109">Na caixa de diálogo suspensa, selecione a opção **Modelo de documento tributável derivado de Nome: modelo de dados de imposto — Europa, Microsoft**, insira um nome para o novo modelo de dados de imposto e selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-109">In the drop-down dialog box, select the **Taxable document model derived from Name: Tax Data Model -- Europe, Microsoft** option, enter a name for the new tax data model, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="ddf5d-110">Selecione o modelo de dados de imposto recém-criado e, no Painel de ação, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-110">Select the tax data model that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="ddf5d-111">Expanda a árvore do modelo de dados, selecione **Linhas** e **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-111">Expand the data model tree, select **Lines**, and then select **New**.</span></span>
6. <span data-ttu-id="ddf5d-112">Na caixa de diálogo **Criar nó**, insira um nome, especifique o tipo de item e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-112">In the **Create node** dialog box, enter a name, specify the item type, and then select **Add**.</span></span>
7. <span data-ttu-id="ddf5d-113">Adicione as colunas necessárias.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-113">Add any required columns.</span></span>
8. <span data-ttu-id="ddf5d-114">No Painel de ações, selecione **Salvar** e **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-114">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="ddf5d-115">Feche a página e veja a versão completa do modelo de dados de imposto.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-115">Close the page, and view the completed version of your tax data model.</span></span>

## <a name="customize-the-tax-configuration"></a><span data-ttu-id="ddf5d-116">Personalize a configuração de imposto</span><span class="sxs-lookup"><span data-stu-id="ddf5d-116">Customize the tax configuration</span></span>

1. <span data-ttu-id="ddf5d-117">Em Finanças , acesse **Relatório Eletrônico** \> **Configurações de impostos**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-117">In Finance, go to **Electronic reporting** \> **Tax configurations**.</span></span>
2. <span data-ttu-id="ddf5d-118">Na árvore de configuração, selecione **Configuração de imposto — Europa**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-118">In the configuration tree, select **Tax Configuration -- Europe**.</span></span> <span data-ttu-id="ddf5d-119">Em seguida, no Painel de Ações, selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-119">Then, on the Action Pane, select **Create configuration**.</span></span>
3. <span data-ttu-id="ddf5d-120">Na caixa de diálogo suspensa, selecione a opção **Configuração de serviço de impostos derivada de Nome: configuração de dados de imposto — Europa, Microsoft**, insira um nome para a nova configuração de impostos e selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-120">In the drop-down dialog box, select the **Tax service configuration derived from Name: Tax Configuration -- Europe, Microsoft** option, enter a name for the new tax configuration, and then select **Create configuration**.</span></span>
4. <span data-ttu-id="ddf5d-121">Selecione a configuração de impostos recém-criada e, no Painel de ação, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-121">Select the tax configuration that you just created, and then, on the Action Pane, select **Designer**.</span></span>
5. <span data-ttu-id="ddf5d-122">Na seção **Propriedades**, no campo **Modelo de dados**, selecione o modelo de dados de impostos personalizado criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-122">In the **Properties** section, in the **Data model** field, select the customized tax data model that you created earlier.</span></span>
6. <span data-ttu-id="ddf5d-123">No campo **Versão do modelo de dados**, selecione a versão completa do modelo de dados de imposto.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-123">In the **Data model version** field, select the completed version of the tax data model.</span></span>
7. <span data-ttu-id="ddf5d-124">Selecione **Adicionar** e adicione os cálculos de imposto necessários.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-124">Select **Add**, and add the required tax measures.</span></span>
8. <span data-ttu-id="ddf5d-125">No Painel de ações, selecione **Salvar** e **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-125">On the Action Pane, select **Save**, and then select **Complete**.</span></span>
9. <span data-ttu-id="ddf5d-126">Feche a página e veja a versão completa da configuração de impostos.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-126">Close page, and view the completed version of your tax configuration.</span></span>

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a><span data-ttu-id="ddf5d-127">Implemente os recursos de imposto na configuração de impostos personalizada</span><span class="sxs-lookup"><span data-stu-id="ddf5d-127">Implement tax features in the customized tax configuration</span></span>

1. <span data-ttu-id="ddf5d-128">Em Regulatory Configuration Services (RCS), acesse **Recursos de globalização** \> **Imposto**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-128">In Regulatory Configuration Service (RCS), go to **Globalization Features** \> **Tax**.</span></span>
2. <span data-ttu-id="ddf5d-129">Selecione **Adicionar**, insira as informações sobre o novo recurso e selecione **Criar recurso**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-129">Select **Add**, enter information about the new feature, and then select **Create feature**.</span></span>
3. <span data-ttu-id="ddf5d-130">Na guia **Versões**, selecione o recurso e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-130">On the **Versions** tab, select the feature, and then select **Edit**.</span></span>
4. <span data-ttu-id="ddf5d-131">Na guia **Geral**, no campo **Versão de configuração**, selecione a configuração de impostos personalizada e a versão.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-131">On the **General** tab, in the **Configuration version** field, select the customized tax configuration and version.</span></span>
5. <span data-ttu-id="ddf5d-132">Na caixa de diálogo **Gerenciar colunas**, selecione o cabeçalho e as colunas que deseja incluir na medida no cálculo de impostos personalizado. Em seguida, selecione o botão de seta para a direita e adicione-as à lista **Colunas selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="ddf5d-132">In the **Manage columns** dialog box, select the header and line columns that you want to include in your customized tax measure, and then select the right arrow button to add them to the **Selected columns** list.</span></span>
