---
title: Declaração de imposto retido na fonte para o Egito
description: Este tópico explica como configurar e gerar as declarações de imposto retido na fonte para o Egito.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e0d13a2de9acaa8b1c896e130b4dabb222e45dcb
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881413"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a><span data-ttu-id="63dfd-103">Declaração de imposto retido na fonte para o Egito (EG-00005)</span><span class="sxs-lookup"><span data-stu-id="63dfd-103">Withholding tax declaration for Egypt (EG-00005)</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a><span data-ttu-id="63dfd-104">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="63dfd-104">Overview</span></span>
<span data-ttu-id="63dfd-105">Este tópico explica como configurar e gerar a declaração de imposto retido na fonte e os formulários de declaração de imposto retido na fonte 41 e 11 para entidades legais no Egito</span><span class="sxs-lookup"><span data-stu-id="63dfd-105">This topic explains how to set up and generate the withholding tax declaration and the withholding tax declaration forms 41 and 11 for legal entities in Egypt</span></span> 

<span data-ttu-id="63dfd-106">Todas as entidades egípcias devem preparar o formulário 41, que resume todos os impostos que são retidos de fornecedores locais e provedores de serviço.</span><span class="sxs-lookup"><span data-stu-id="63dfd-106">All Egyptian entities must prepare the form  41 which summarizes all taxes that are retained from local suppliers and service providers.</span></span> <span data-ttu-id="63dfd-107">Além do formulário 41, o formulário 11 deve ser gerado para detalhar todos os impostos retidos de fornecedores estrangeiros.</span><span class="sxs-lookup"><span data-stu-id="63dfd-107">In addition to form 41, form 11 must be generated to detail all of the retained taxed from foreign providers.</span></span> 

<span data-ttu-id="63dfd-108">O relatório **Declaração de imposto retido na fonte** no Dynamics 365 Finance inclui os seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="63dfd-108">The **Withholding tax declaration** report in Dynamics 365 Finance includes the following reports:</span></span>

- <span data-ttu-id="63dfd-109">Nº do formulário de declaração</span><span class="sxs-lookup"><span data-stu-id="63dfd-109">Declaration form No.</span></span> <span data-ttu-id="63dfd-110">41</span><span class="sxs-lookup"><span data-stu-id="63dfd-110">41</span></span>
- <span data-ttu-id="63dfd-111">Nº do formulário de declaração</span><span class="sxs-lookup"><span data-stu-id="63dfd-111">Declaration form No.</span></span> <span data-ttu-id="63dfd-112">11</span><span class="sxs-lookup"><span data-stu-id="63dfd-112">11</span></span>
    
    
## <a name="prerequisites"></a><span data-ttu-id="63dfd-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="63dfd-113">Prerequisites</span></span>
<span data-ttu-id="63dfd-114">O público-alvo principal da entidade legal deve estar no Egito.</span><span class="sxs-lookup"><span data-stu-id="63dfd-114">The primary address of the legal entity must be in Egypt.</span></span>
<span data-ttu-id="63dfd-115">No espaço de trabalho **Gerenciamento de recursos**, o recurso a seguir deve estar habilitado:</span><span class="sxs-lookup"><span data-stu-id="63dfd-115">In the **Feature management** workspace, the following feature must be enabled:</span></span>

   - <span data-ttu-id="63dfd-116">**Imposto retido na fonte global**</span><span class="sxs-lookup"><span data-stu-id="63dfd-116">**Global withholding tax**</span></span>

<span data-ttu-id="63dfd-117">Para obter mais informações sobre como habilitar recursos, consulte [Visão geral do gerenciamento de recursos.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="63dfd-117">For more information about how to enable features, see [Feature management overview.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span></span>

1. <span data-ttu-id="63dfd-118">Acesse **Imposto** > **Configuração** > **Parâmetros** > **Parâmetros de Contabilidade** e, na guia **Imposto retido na fonte**, defina **Habilitar imposto retido na fonte global** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-118">Go to **Tax** > **Setup** > **Parameters** > **General ledger parameters**, and on the **Withholding tax** tab, set **Enable global withholding tax** to **Yes**.</span></span>
2. <span data-ttu-id="63dfd-119">No espaço de trabalho **Relatório eletrônico**, importe os seguintes formatos de Relatório eletrônicos do repositório:</span><span class="sxs-lookup"><span data-stu-id="63dfd-119">In the **Electronic reporting** workspace, import the following Electronic reporting formats from the repository:</span></span>

    - <span data-ttu-id="63dfd-120">Declaração WHT Excel (EG)</span><span class="sxs-lookup"><span data-stu-id="63dfd-120">WHT Declaration Excel (EG)</span></span>

    > [!NOTE]
    > <span data-ttu-id="63dfd-121">O formato acima se baseia no **modelo Declaração de impostos** e usa o **mapeamento de modelos Declaração de imposto**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-121">The format above is based on the **Tax declaration model** and uses the **Tax declaration model mapping**.</span></span> <span data-ttu-id="63dfd-122">Essa configuração adicional é importada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="63dfd-122">This additional configuration is automatically imported.</span></span>

<span data-ttu-id="63dfd-123">Para obter mais informações sobre como importar configurações de Relatório eletrônico, consulte [Baixar configurações de Relatório eletrônico do Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="63dfd-123">For more information about how to import Electronic reporting configurations, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

## <a name="download-electronic-reporting-configurations"></a><span data-ttu-id="63dfd-124">Baixar configurações de Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="63dfd-124">Download Electronic reporting configurations</span></span>

<span data-ttu-id="63dfd-125">A implementação dos formulários de declaração WHT para o Egito baseia-se em configurações de Relatório eletrônico (ER).</span><span class="sxs-lookup"><span data-stu-id="63dfd-125">The implementation of the WHT declaration forms for Egypt is based on Electronic reporting (ER) configurations.</span></span> <span data-ttu-id="63dfd-126">Para obter mais informações sobre os recursos e conceitos de relatórios configuráveis, consulte [Relatórios eletrônicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="63dfd-126">For more information about the capabilities and concepts of configurable reporting, see [Electronic reporting](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span></span>

<span data-ttu-id="63dfd-127">Para ambientes de produção e de teste de aceitação de usuários (UAT), siga as instruções no tópico [Baixar configurações de Relatório eletrônico do Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="63dfd-127">For production and user acceptance testing (UAT) environments, follow the instructions in the topic, [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

<span data-ttu-id="63dfd-128">Para gerar as Declarações de retenção em uma entidade legal egípcia, é necessário carregar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="63dfd-128">To generate the Withholding declarations in an Egyptian legal entity, you need to upload the following configurations:</span></span>

- <span data-ttu-id="63dfd-129">Declaração de imposto modelo.versão.82.xml ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="63dfd-129">Tax declaration model.version.82.xml or later version</span></span>
- <span data-ttu-id="63dfd-130">Modelo de declaração de imposto mapeamento.versão.82.133.xml ou uma versão posterior</span><span class="sxs-lookup"><span data-stu-id="63dfd-130">Tax declaration model mapping.version.82.133.xml or a later version</span></span>
- <span data-ttu-id="63dfd-131">Declaração WHT Excel (EG).versão.82.21 ou uma versão posterior</span><span class="sxs-lookup"><span data-stu-id="63dfd-131">WHT Declaration Excel (EG).version.82.21  or a later version</span></span>

<span data-ttu-id="63dfd-132">Depois de terminar de baixar as configurações de ER do Lifecycle Services (LCS) ou do repositório global, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="63dfd-132">After you finish downloading the ER configurations from Lifecycle Services (LCS) or the global repository, complete the following steps.</span></span>

1. <span data-ttu-id="63dfd-133">Acesse o espaço de trabalho **Relatório eletrônico** e selecione o bloco **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-133">Go to the **Electronic reporting** workspace and select the **Reporting configurations** tile.</span></span>
1. <span data-ttu-id="63dfd-134">Na página **Configurações**, no Painel de Ações, selecione **Troca > Carregar de arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-134">On the **Configurations** page, on the Action Pane, select **Exchange > Load from XML file**.</span></span>
1. <span data-ttu-id="63dfd-135">Carregue todos os arquivos na ordem em que estão listados nos marcadores anteriores.</span><span class="sxs-lookup"><span data-stu-id="63dfd-135">Upload all the files in the order in which they are listed in the previous bullets.</span></span> <span data-ttu-id="63dfd-136">Depois que todas as configurações são carregadas, a árvore de configuração deve estar presente no Finance.</span><span class="sxs-lookup"><span data-stu-id="63dfd-136">After all of the configurations are uploaded, the configuration tree should be present in Finance.</span></span>

## <a name="set-up-application-specific-parameters"></a><span data-ttu-id="63dfd-137">Configurar parâmetros específicos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="63dfd-137">Set up application-specific parameters</span></span>

<span data-ttu-id="63dfd-138">A opção de parâmetros específicos do aplicativo permite que os usuários estabeleçam os critérios de como as transações de imposto serão classificadas e calculadas em cada linha de um relatório gerado, dependendo da configuração do **grupo de itens de imposto retido na fonte** ou de outros critérios estabelecidos na definição de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63dfd-138">The application-specific parameters option lets users establish the criteria of how the tax transactions will be classified and calculated in each line of a generated report depending on the configuration of **withholding tax item group** or other criteria established in the definition of lookup.</span></span>

<span data-ttu-id="63dfd-139">O formulário 41 de imposto retido na fonte inclui uma coluna específica na qual a transação de imposto retido na fonte deve ser classificada de acordo com a classificação de autoridade de imposto chamada **Tipo de código de desconto**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-139">Withholding declaration form 41 includes a specific column where the withholding tax transaction must be classified in accordance with the tax authority classification named **Discount code type**.</span></span> <span data-ttu-id="63dfd-140">Em vez de incluir essas novas classificações como novos dados de entrada quando as transações são lançadas, as classificações serão determinadas com base nas diferentes pesquisas introduzidas em **Configurações** > **Configurar parâmetros específicos do aplicativo** > **Configuração** para atender aos requisitos de relatórios de retenção para o Egito.</span><span class="sxs-lookup"><span data-stu-id="63dfd-140">Instead of including these new classifications as new entry data when the transactions are posted, the classifications will be determined based on the different lookups introduced in **Configurations** > **Set up application-specific parameters** > **Setup** to meet the requirements of withholding reports for Egypt.</span></span> 

<span data-ttu-id="63dfd-141">A configuração a seguir é usada para classificar as transações no formulário 41 Declaração de retenção.</span><span class="sxs-lookup"><span data-stu-id="63dfd-141">The following configuration is used to classify the transactions in the Withholding declaration form 41 report:</span></span>

- <span data-ttu-id="63dfd-142">**DiscountTaxTypeLookup**-> Coluna Nº 18</span><span class="sxs-lookup"><span data-stu-id="63dfd-142">**DiscountTaxTypeLookup**-> Column No 18</span></span> 

<span data-ttu-id="63dfd-143">Conclua as etapas a seguir para configurar as diferentes pesquisas usadas para gerar a declaração WHT e os livros fiscais relacionados.</span><span class="sxs-lookup"><span data-stu-id="63dfd-143">Complete the following steps to set up the different lookups used to generate the WHT declaration and related books reports.</span></span> 

1. <span data-ttu-id="63dfd-144">No espaço de trabalho **Relatório eletrônico**, selecione **Configurações** > **Configuração** para configurar as regras para identificar como as transações são classificadas no relatório de declaração WHT.</span><span class="sxs-lookup"><span data-stu-id="63dfd-144">In the **Electronic reporting** workspace, select **Configurations** > **Setup** to set up the rules to identify how transactions are classified in the WHT declaration report.</span></span> 
2. <span data-ttu-id="63dfd-145">Selecione a versão atual e, na Guia Rápida **Pesquisas**, selecione o nome da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63dfd-145">Select the current version, and on the **Lookups** FastTab, select the lookup name.</span></span> <span data-ttu-id="63dfd-146">Por exemplo, **DiscountTaxTypeLookup**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-146">For example, **DiscountTaxTypeLookup**.</span></span> <span data-ttu-id="63dfd-147">Essa pesquisa identifica a lista de tipos de desconto exigidos pela autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="63dfd-147">This lookup identifies the list of discount types required by the tax authority.</span></span>
3. <span data-ttu-id="63dfd-148">Na Guia Rápida **Condições**, selecione **Adicionar** e, na nova linha na coluna **Resultado da pesquisa**, selecione a linha relacionada que representa a classificação na **Coluna 18**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-148">On the **Conditions** FastTab, select **Add** and in the new line in the **Lookup result** column, select the related line that represents the classification in the **Column 18**.</span></span>
4. <span data-ttu-id="63dfd-149">Na coluna **Grupo de itens de imposto retido na fonte**, selecione o código relacionado que é usado para identificar a classificação.</span><span class="sxs-lookup"><span data-stu-id="63dfd-149">In the **Withholding tax item group** column, select the related code that's used to identify the classification.</span></span> <span data-ttu-id="63dfd-150">Por exemplo, **Desconto permitido**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-150">For example, **Allowed discount**.</span></span>  
5. <span data-ttu-id="63dfd-151">Repita as etapas 3 e 4 para todas as pesquisas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="63dfd-151">Repeat steps 3 and 4 for all available lookups.</span></span>
6. <span data-ttu-id="63dfd-152">Selecione **Adicionar** novamente para incluir a linha de registro final e, na coluna **Resultado da pesquisa**, selecione **Não aplicável**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-152">Select **Add** again to include the final record line, and in the **Lookup result** column, select **Not applicable**.</span></span> 
7. <span data-ttu-id="63dfd-153">Nas colunas restantes, selecione **Não vazio**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-153">In the remaining columns, select **Not blank**.</span></span> 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a><span data-ttu-id="63dfd-154">Configurar parâmetros de Contabilidade</span><span class="sxs-lookup"><span data-stu-id="63dfd-154">Set up General ledger parameters</span></span>

<span data-ttu-id="63dfd-155">Para gerar os relatórios do formulário de declaração WHT no Microsoft Excel, defina um formato ER na página **Parâmetros da Contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-155">To generate the WHT declaration form reports in Microsoft Excel, define an ER format on the **General ledger parameters** page.</span></span>

1. <span data-ttu-id="63dfd-156">Acesse **Imposto** > **Configuração** > **Parâmetros de Contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-156">Go to **Tax** > **Setup** > **General ledger parameters**.</span></span>
2. <span data-ttu-id="63dfd-157">Na guia **Imposto retido na fonte**, no campo **Mapeamento de formato de declaração WHT**, selecione **Declaração WHT Excel (EG)**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-157">On the **Withholding tax** tab, in the **WHT declaration format mapping** field, select **WHT Declaration Excel (EG)**.</span></span> <span data-ttu-id="63dfd-158">Se você deixar o campo em branco, o relatório de imposto padrão será gerado no formato SSRS.</span><span class="sxs-lookup"><span data-stu-id="63dfd-158">If you leave the field blank, the standard sales tax report will be generated in SSRS format.</span></span>


![Formulário de declaração](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a><span data-ttu-id="63dfd-160">Gerar os formulários Declaração de retenção</span><span class="sxs-lookup"><span data-stu-id="63dfd-160">Generate the Withholding declaration forms</span></span>
<span data-ttu-id="63dfd-161">O processo de preparação e de envio de um formulário Declaração de retenção para um período específico é baseado nas transações de retenção de imposto lançadas durante a liquidação e lançar o trabalho de imposto de pagamento.</span><span class="sxs-lookup"><span data-stu-id="63dfd-161">The process of preparing and submitting a Withholding declaration form for a specific period is based on the withholding tax transactions posted during the settle and post payment tax job.</span></span> <span data-ttu-id="63dfd-162">Para obter mais informações sobre imposto retido na fonte global, consulte [Imposto retido na fonte global](../general-ledger/global-withholding-tax-overview.md).</span><span class="sxs-lookup"><span data-stu-id="63dfd-162">For more information about global withholding tax, see [Global withholding tax](../general-ledger/global-withholding-tax-overview.md).</span></span>

<span data-ttu-id="63dfd-163">Conclua as etapas a seguir para gerar o relatório de declaração de impostos.</span><span class="sxs-lookup"><span data-stu-id="63dfd-163">Complete the following steps to generate the tax declaration report.</span></span>

1. <span data-ttu-id="63dfd-164">Acesse **Imposto** > **Declarações** > **Imposto retido na fonte** > \**Pagamento de imposto retido na fonte*.</span><span class="sxs-lookup"><span data-stu-id="63dfd-164">Go to **Tax** > **Declarations** > **Withholding tax** > \**Withholding tax payment*.</span></span>
2. <span data-ttu-id="63dfd-165">Selecione o período de liquidação e selecione a data inicial do relatório.</span><span class="sxs-lookup"><span data-stu-id="63dfd-165">Select the settlement period and then select the from date for the report.</span></span> 
3. <span data-ttu-id="63dfd-166">Insira a data de transação e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-166">Enter the transaction date and then select **OK**.</span></span>
4. <span data-ttu-id="63dfd-167">Na caixa de diálogo que é aberta, selecione um ou mais dos tipos de formulário **Formulário Nº 41**, **Formulário Nº 11** ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-167">In the dialog box that opens, select one or more of the form types \*\*Form No 41 \*\*, **Form No 11**, or **None**.</span></span> <span data-ttu-id="63dfd-168">Se você selecionar **Nenhum**, o relatório padrão será gerado.</span><span class="sxs-lookup"><span data-stu-id="63dfd-168">If you select **None**, the standard report is generated.</span></span> 
5. <span data-ttu-id="63dfd-169">Selecione o idioma.</span><span class="sxs-lookup"><span data-stu-id="63dfd-169">Select the language.</span></span> <span data-ttu-id="63dfd-170">Todos os relatórios são traduzidos em **en-us** e **ar-eg**.</span><span class="sxs-lookup"><span data-stu-id="63dfd-170">All reports are translated in **en-us** and **ar-eg**.</span></span>
6. <span data-ttu-id="63dfd-171">Insira o branch e o nome do banco em que o pagamento de imposto será pago.</span><span class="sxs-lookup"><span data-stu-id="63dfd-171">Enter the branch and name of the bank where the tax payment will be paid.</span></span>
7. <span data-ttu-id="63dfd-172">Selecione o tipo comercial e insira os números de cheque e documento.</span><span class="sxs-lookup"><span data-stu-id="63dfd-172">Select the business type and then enter the check and document numbers.</span></span> 
8. <span data-ttu-id="63dfd-173">Insira o tipo da entidade.</span><span class="sxs-lookup"><span data-stu-id="63dfd-173">Enter the entity type.</span></span> 
9. <span data-ttu-id="63dfd-174">Insira o nome da pessoa registrada para atribuir o formulário e selecione **OK** para confirmar a geração do relatório.</span><span class="sxs-lookup"><span data-stu-id="63dfd-174">Enter the name of person registered to assign the form and select **OK** to confirm the report generation.</span></span> 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
