---
title: "Integração fiscal do canal de varejo"
description: "Este tópico oferece uma visão geral da integração fiscal do Retail POS."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: pt-br
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a><span data-ttu-id="e209c-103">Integração fiscal do canal de varejo</span><span class="sxs-lookup"><span data-stu-id="e209c-103">Fiscal integration for Retail channel</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e209c-104">Este tópico é uma visão geral da funcionalidade de integração fiscal que está disponível no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="e209c-104">This topic is an overview of the fiscal integration functionality that is available in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="e209c-105">A funcionalidade de integração fiscal é uma estrutura criada para dar suporte às leis fiscais locais, visando evitar fraudes no setor de varejo.</span><span class="sxs-lookup"><span data-stu-id="e209c-105">The fiscal integration functionality is a framework designed to support local fiscal laws that are aimed to prevent fraud in the Retail industry.</span></span> <span data-ttu-id="e209c-106">Os cenários típicos que podem ser cobertos usando a integração fiscal incluem:</span><span class="sxs-lookup"><span data-stu-id="e209c-106">Typical scenarios that could be covered by using fiscal integration include:</span></span>

- <span data-ttu-id="e209c-107">Impressão de um recibo fiscal e oferta ao cliente.</span><span class="sxs-lookup"><span data-stu-id="e209c-107">Printing a fiscal receipt and giving it to the customer.</span></span>
- <span data-ttu-id="e209c-108">Proteção do envio das informações relacionadas às vendas e às devoluções realizadas em PDV para um serviço externo oferecido pela autoridade.</span><span class="sxs-lookup"><span data-stu-id="e209c-108">Securing the submission of the information related to sales and returns performed on POS to an external service provided by the authority.</span></span>
- <span data-ttu-id="e209c-109">Uso da proteção de dados com uma assinatura digital autorizada pela autoridade.</span><span class="sxs-lookup"><span data-stu-id="e209c-109">Using data protection with a digital signature authorized by the authority.</span></span>

<span data-ttu-id="e209c-110">Este tópico oferece diretrizes para configurar a integração fiscal para que os usuários possam executar as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e209c-110">This topic provides guidelines for setting up fiscal integration so users can perform the following tasks.</span></span> 

- <span data-ttu-id="e209c-111">Configurar os conectores fiscais, que são os dispositivos ou serviços fiscais usados para fins de registro fiscal, como a salva de assinaturas digitais e o envio protegido de dados fiscais.</span><span class="sxs-lookup"><span data-stu-id="e209c-111">Configure fiscal connectors, which are fiscal devices or services used for fiscal registration purposes like saving, digital signatures, and secured submission of fiscal data.</span></span>
- <span data-ttu-id="e209c-112">Configure o provedor de documentos, que define um método de saída e um algoritmo de geração de documento fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-112">Configure the document provider, which defines an output method and an algorithm of fiscal document generation.</span></span>
- <span data-ttu-id="e209c-113">Configurar o processo de registro fiscal, que define uma sequência de etapas e um grupo de conectores usados em cada etapa.</span><span class="sxs-lookup"><span data-stu-id="e209c-113">Configure the fiscal registration process, which is defines a sequence of steps and a group of connectors used on each step.</span></span>
- <span data-ttu-id="e209c-114">Atribuir processos de registro fiscal aos perfis de funcionalidade de PDV.</span><span class="sxs-lookup"><span data-stu-id="e209c-114">Assign fiscal registration processes to POS functionality profiles.</span></span>
- <span data-ttu-id="e209c-115">Atribuir perfis técnicos de conector para perfis de hardware (para os conectores fiscais locais) ou para perfis de funcionalidade de PDV (para outros tipos de contector fiscal).</span><span class="sxs-lookup"><span data-stu-id="e209c-115">Assign connector technical profiles, either to hardware profiles (for the local fiscal connectors) or to POS functionality profiles (for other fiscal connector types).</span></span>

## <a name="fiscal-integration-execution-flow"></a><span data-ttu-id="e209c-116">Fluxo de execução de integração fiscal</span><span class="sxs-lookup"><span data-stu-id="e209c-116">Fiscal integration execution flow</span></span>
<span data-ttu-id="e209c-117">O cenário a seguir mostra o fluxo de execução de integração fiscal comum.</span><span class="sxs-lookup"><span data-stu-id="e209c-117">The following scenario shows the common fiscal integration execution flow.</span></span>

1. <span data-ttu-id="e209c-118">Inicialização do processo de registro fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-118">Initialization of the fiscal registration process.</span></span>
  
   <span data-ttu-id="e209c-119">Depois de executar algumas ações onde o registro fiscal é necessário, como após uma transação de varejo ser concluída, o processo de registro fiscal é associado ao perfil atual de funcionalidade de PDV.</span><span class="sxs-lookup"><span data-stu-id="e209c-119">After performing some actions where fiscal registration is required, such as after a retail transaction has been concluded, the fiscal registration process is associated with the current POS functionality profile.</span></span>

1. <span data-ttu-id="e209c-120">Procure um conector fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-120">Search for a fiscal connector.</span></span>
   
   <span data-ttu-id="e209c-121">Para cada etapa do registro fiscal incluída no processo de registro fiscal, o sistema coincide a lista de conectores fiscais.</span><span class="sxs-lookup"><span data-stu-id="e209c-121">For each fiscal registration step included in the fiscal registration process, the system matches the list of fiscal connectors.</span></span> <span data-ttu-id="e209c-122">Esses conectores têm um perfil funcional incluído no grupo de conectores especificado, com uma lista de conectores com um perfil técnico associado ao perfil de hardware atual (de um tipo de conector que seja apenas igual a **Local**) ou com o perfil atual de funcionalidade de PDV (para outros tipos de conector).</span><span class="sxs-lookup"><span data-stu-id="e209c-122">These connectors have a functional profile included in the specified connector group, with a list of connectors that have a technical profile associated with the current hardware profile (for a connector type that equals **Local** only) or with the current POS functionality profile (for other connector types).</span></span>
   
1. <span data-ttu-id="e209c-123">Executar a integração fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-123">Perform the fiscal integration.</span></span>

   <span data-ttu-id="e209c-124">O sistema executa todas as ações necessárias definidas por um assembly vinculado ao conector encontrado.</span><span class="sxs-lookup"><span data-stu-id="e209c-124">The system executes all necessary actions defined by an assembly linked with the found connector.</span></span> <span data-ttu-id="e209c-125">Isso é feito de acordo com as configurações do perfil funcional funcional e do perfil técnico que foram encontrados na etapa anterior para esse conector.</span><span class="sxs-lookup"><span data-stu-id="e209c-125">This is done in accordance with the settings of the functional profile and technical profile that were found on the previous step for this connector.</span></span>

## <a name="setup-needed-before-using-fiscal-integration"></a><span data-ttu-id="e209c-126">Configuração necessária antes de usar a integração fiscal</span><span class="sxs-lookup"><span data-stu-id="e209c-126">Setup needed before using fiscal integration</span></span>
<span data-ttu-id="e209c-127">Antes de usar a funcionalidade de integração fiscal, você deve definir estas configurações:</span><span class="sxs-lookup"><span data-stu-id="e209c-127">Before using the fiscal integration functionality, you should define the following settings:</span></span>

- <span data-ttu-id="e209c-128">Defina a sequência numérica na página **Parâmetros de varejo** para o número de perfil funcional fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-128">Define the number sequence on the **Retail parameters** page for the fiscal functional profile number.</span></span>
  
- <span data-ttu-id="e209c-129">Defina as sequências numéricas na página **Parâmetros compartilhados de varejo** para as seguintes referências:</span><span class="sxs-lookup"><span data-stu-id="e209c-129">Define the number sequences on the **Retail shared parameters** page for the following references:</span></span>
  
  - <span data-ttu-id="e209c-130">Número do perfil técnico fiscal</span><span class="sxs-lookup"><span data-stu-id="e209c-130">Fiscal technical profile number</span></span>
  - <span data-ttu-id="e209c-131">Número do grupo do conector fiscal</span><span class="sxs-lookup"><span data-stu-id="e209c-131">Fiscal connector group number</span></span>
  - <span data-ttu-id="e209c-132">Número do processo de registro</span><span class="sxs-lookup"><span data-stu-id="e209c-132">Registration process number</span></span>

- <span data-ttu-id="e209c-133">Crie um **Conector fiscal** em **Varejo > Configuração de canal > integração fiscal > Conectores fiscais** para cada dispositivo ou serviço que você pretenda usar para fins de integração fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-133">Create a **Fiscal connector** in **Retail > Channel setup > Fiscal integration > Fiscal connectors** for each device or service that you plan to use for fiscal integration purposes.</span></span>

-  <span data-ttu-id="e209c-134">Crie um **Provedor de documento fiscal** em **Varejo > Configuração de canal > Integração fiscal > Provedores de documento fsical** para todos os conectores fiscais.</span><span class="sxs-lookup"><span data-stu-id="e209c-134">Create a **Fiscal document provider** in **Retail > Channel setup > Fiscal integration > Fiscal document providers** for all fiscal connectors.</span></span> <span data-ttu-id="e209c-135">O mapeamento de dados é considerado parte do provedor de documento fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-135">Data mapping is considered a part of the fiscal document provider.</span></span> <span data-ttu-id="e209c-136">Para configurar diferentes mapeamentos de dados para o mesmo conector (como regulamentações específicas de estado), crie diferentes provedores de documento fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-136">To set up different data mappings for the same connector (like state-specific regulations), you should create different fiscal document providers.</span></span>

- <span data-ttu-id="e209c-137">Crie um **Perfil funcional de conector** em **Varejo > Configuração de canal > Integração fiscal > Perfis funcionais de conector** para cada fornecedor de documento fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-137">Create a **Connector functional profile** in **Retail > Channel setup > Fiscal integration > Connector functional profiles** for each fiscal document provider.</span></span>
  - <span data-ttu-id="e209c-138">Selecione um nome de conector.</span><span class="sxs-lookup"><span data-stu-id="e209c-138">Select a connector name.</span></span>
  - <span data-ttu-id="e209c-139">Selecione um provedor de documento.</span><span class="sxs-lookup"><span data-stu-id="e209c-139">Select a document provider.</span></span>
  - <span data-ttu-id="e209c-140">Especifique configurações de alíquota de IVA na guia **Configuração de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e209c-140">Specify VAT rates settings on the **Service setup** tab.</span></span>
  - <span data-ttu-id="e209c-141">Especifique o mapeamento de códigos IVA e o mapeamento de tipo de meio de pagamento na guia **Mapeamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="e209c-141">Specify VAT codes mapping and tender type mapping on the **Data mapping** tab.</span></span>

  #### <a name="examples"></a><span data-ttu-id="e209c-142">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e209c-142">Examples</span></span> 

  |  | <span data-ttu-id="e209c-143">Formatar</span><span class="sxs-lookup"><span data-stu-id="e209c-143">Format</span></span> | <span data-ttu-id="e209c-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e209c-144">Example</span></span> | 
  |--------|--------|--------|
  | <span data-ttu-id="e209c-145">Configurações de alíquotas de IVA</span><span class="sxs-lookup"><span data-stu-id="e209c-145">VAT rates settings</span></span> | <span data-ttu-id="e209c-146">valor: VATrate</span><span class="sxs-lookup"><span data-stu-id="e209c-146">value : VATrate</span></span> | <span data-ttu-id="e209c-147">1 : 2000, 2 : 1800</span><span class="sxs-lookup"><span data-stu-id="e209c-147">1 : 2000, 2 : 1800</span></span> |
  | <span data-ttu-id="e209c-148">Mapeamento dos códigos IVA</span><span class="sxs-lookup"><span data-stu-id="e209c-148">VAT codes mapping</span></span> | <span data-ttu-id="e209c-149">VATcode : valor</span><span class="sxs-lookup"><span data-stu-id="e209c-149">VATcode : value</span></span> | <span data-ttu-id="e209c-150">vat20 : 1, vat18 : 2</span><span class="sxs-lookup"><span data-stu-id="e209c-150">vat20 : 1, vat18 : 2</span></span> |
  | <span data-ttu-id="e209c-151">Mapeamento de tipos de meio de pagamento</span><span class="sxs-lookup"><span data-stu-id="e209c-151">Tender types mapping</span></span> | <span data-ttu-id="e209c-152">TenderTyp: valor</span><span class="sxs-lookup"><span data-stu-id="e209c-152">TenderTyp : value</span></span> | <span data-ttu-id="e209c-153">Caixa: 1, cartão: 2</span><span class="sxs-lookup"><span data-stu-id="e209c-153">Cash : 1, Card : 2</span></span> |

- <span data-ttu-id="e209c-154">Crie **Grupos de conectores fiscais** em **Varejo > Configuração de canal > Integração fiscal > Grupo de conectores fiscais**.</span><span class="sxs-lookup"><span data-stu-id="e209c-154">Create **Fiscal connector groups** in **Retail > Channel setup > Fiscal integration > Fiscal connector group**.</span></span> <span data-ttu-id="e209c-155">Um grupo de conectores é um subconjunto de perfis funcionais vinculados a conectores fiscais que executam funções idênticas e são usados no mesmo estágio em um processo de registro fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-155">A connector group is a subset of functional profiles linked with fiscal connectors that perform identical functions and are used at the same stage within a fiscal registration process.</span></span>

   - <span data-ttu-id="e209c-156">Adicione perfis funcionais ao grupo de conectores.</span><span class="sxs-lookup"><span data-stu-id="e209c-156">Add functional profiles to the connector group.</span></span> <span data-ttu-id="e209c-157">Clique em **Adicionar** na página **Perfis funcionais** e selecione um número do perfil.</span><span class="sxs-lookup"><span data-stu-id="e209c-157">Click **Add** on the **Functional profiles** page and select a profile number.</span></span>
   - <span data-ttu-id="e209c-158">Se desejar suspender o uso do perfil funcional, defina **Desabilitar** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e209c-158">If you want to suspend usage of the functional profile, set **Disable** to **Yes**.</span></span> 
   
     <span data-ttu-id="e209c-159">Esta alteração afeta apenas o grupo de conectores atual.</span><span class="sxs-lookup"><span data-stu-id="e209c-159">This change affects the current connector group only.</span></span> <span data-ttu-id="e209c-160">Você pode continuar usando o mesmo perfil funcional em outros grupos de conectores.</span><span class="sxs-lookup"><span data-stu-id="e209c-160">You can continue using the same functional profile in other connector groups.</span></span>

     >[!NOTE]
     > <span data-ttu-id="e209c-161">Em um grupo de conectores, cada conector fiscal só pode ter um perfil funcional.</span><span class="sxs-lookup"><span data-stu-id="e209c-161">Within a connector group, each fiscal connector can only have one functional profile.</span></span>

- <span data-ttu-id="e209c-162">Crie um **Perfil técnico do conector** em **Varejo > Configuração de canal > Integração fiscal > Perfis técnicos do conector** para cada conector fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-162">Create a **Connector technical profile** in **Retail > Channel setup > Fiscal integration > Connector technical profiles** for each fiscal connector.</span></span>
  - <span data-ttu-id="e209c-163">Selecione um nome de conector.</span><span class="sxs-lookup"><span data-stu-id="e209c-163">Select a connector name.</span></span>
  - <span data-ttu-id="e209c-164">Selecione um tipo de conector:</span><span class="sxs-lookup"><span data-stu-id="e209c-164">Select a connector type:</span></span> 
      - <span data-ttu-id="e209c-165">**Local** - Configure este tipo de dispositivos físicos ou aplicativos instalados em um computador local.</span><span class="sxs-lookup"><span data-stu-id="e209c-165">**Local** - Set this type for physical devices or applications installed on a local machine.</span></span>
      - <span data-ttu-id="e209c-166">**Interno** - Configure este tipo de dispositivos e serviços fiscais conectados ao Retail Server.</span><span class="sxs-lookup"><span data-stu-id="e209c-166">**Internal** - Set this type for fiscal devices and services connected to Retail Server.</span></span>
      - <span data-ttu-id="e209c-167">**Externo** - Para serviços fiscais externos como um portal da Web fornecido por uma autoridade de impostos.</span><span class="sxs-lookup"><span data-stu-id="e209c-167">**External** - For external fiscal services like a web-portal provided by a tax authority.</span></span>
    
  - <span data-ttu-id="e209c-168">Especifique configurações na guia **Conexão**.</span><span class="sxs-lookup"><span data-stu-id="e209c-168">Specify settings on the **Connection** tab.</span></span>

      
 >[!NOTE]
 > <span data-ttu-id="e209c-169">Uma versão atualizada de uma configuração que foi carregada antes será carregada para perfis funcionais e técnicos.</span><span class="sxs-lookup"><span data-stu-id="e209c-169">An updated version of a configuration that was loaded earlier will be loaded for both functional and technical profiles.</span></span> <span data-ttu-id="e209c-170">Se um conector apropriado ou provedor de documentos já estiver em uso, você será notificado.</span><span class="sxs-lookup"><span data-stu-id="e209c-170">If an appropriate connector or document provider is already in use, you will be notified.</span></span> <span data-ttu-id="e209c-171">Por padrão, todas as alterações feitas manualmente em perfis funcionais e técnicos serão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="e209c-171">By default, all changes that have been made manually in functional and technical profiles will be stored.</span></span> <span data-ttu-id="e209c-172">Para substituir esses perfis pelo conjunto padrão de parâmetros de uma configuração, clique em **Atualizar** na página **Perfis funcionais do conector** e na página **Perfis técnicos do conector**.</span><span class="sxs-lookup"><span data-stu-id="e209c-172">In order to override these profiles with the default set of parameters from a configuration, click **Update** on the **Connector functional profiles** page and **Connector technical profiles** page.</span></span>
 
- <span data-ttu-id="e209c-173">Crie um **Processo de registro fiscal** em **Varejo > Configuração de canal > Integração fiscal > Processos de registros fiscais** para cada processo exclusivo da integração fiscal.</span><span class="sxs-lookup"><span data-stu-id="e209c-173">Create a **Fiscal registration process** in **Retail > Channel setup > Fiscal integration > Fiscal registration processes** for each unique process of the fiscal integration.</span></span> <span data-ttu-id="e209c-174">Um processo de registro é definido pela sequência das etapas de registro e do grupo de conectores usados em cada etapa.</span><span class="sxs-lookup"><span data-stu-id="e209c-174">A registration process is defined by the sequence of the registration steps and the connector group used on each step.</span></span> 
  
  - <span data-ttu-id="e209c-175">Adicione as etapas do registro ao processo:</span><span class="sxs-lookup"><span data-stu-id="e209c-175">Add registration steps to the process:</span></span>
      - <span data-ttu-id="e209c-176">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e209c-176">Click **Add**.</span></span>
      - <span data-ttu-id="e209c-177">Selecione um tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="e209c-177">Select a connector type.</span></span>
      
      >[!NOTE]
      > <span data-ttu-id="e209c-178">Este campo define onde o sistema pesquisará em um perfil técnico para o conector, em perfis de hardware para o tipo de conector **Local**ou em perfis de funcionalidade de PDV para outros tipos de conectores fiscais.</span><span class="sxs-lookup"><span data-stu-id="e209c-178">This field defines where the system will search in a technical profile for the connector, either in hardware profiles for connector type **Local**, or in POS functionality profiles for other fiscal connector types.</span></span>
      
   - <span data-ttu-id="e209c-179">Selecione um grupo de conectores.</span><span class="sxs-lookup"><span data-stu-id="e209c-179">Select a connector group.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="e209c-180">Clique em **Validar** para verificar a integridade da estrutura do processo de registro.</span><span class="sxs-lookup"><span data-stu-id="e209c-180">Click **Validate** to check the integrity of the registration process structure.</span></span> <span data-ttu-id="e209c-181">É recomendável que validações sejam feitas nos seguintes casos:</span><span class="sxs-lookup"><span data-stu-id="e209c-181">It’s recommended that validations be made in the following cases:</span></span>
       >- <span data-ttu-id="e209c-182">Para um novo processo de registro após todas as configurações serem concluídas, inclusive a associação de perfis de funcionalidade de PDV e perfis de hardware.</span><span class="sxs-lookup"><span data-stu-id="e209c-182">For a new registration process after all the settings are completed, including binding to POS functionality profiles and hardware profiles.</span></span>
       >- <span data-ttu-id="e209c-183">Após fazer atualizações em um processo de registro existente.</span><span class="sxs-lookup"><span data-stu-id="e209c-183">After making updates to an existing registration process.</span></span>

-  <span data-ttu-id="e209c-184">Associe processos de registro fiscal a perfis de funcionalidade de PDV em **Varejo > Configuração de canal > Configuração do PDV > Perfis de PDV > Perfis de funcionalidade**.</span><span class="sxs-lookup"><span data-stu-id="e209c-184">Bind fiscal registration processes to POS functionality profiles in **Retail > Channel setup > POS setup > POS profiles > Functionality profiles**.</span></span>
   - <span data-ttu-id="e209c-185">Clique em **Editar** e selecione um **Número do processo** na guia **Processo de registro fiscal**.</span><span class="sxs-lookup"><span data-stu-id="e209c-185">Click **Edit** and select a **Process number** on the **Fiscal registration process** tab.</span></span>
- <span data-ttu-id="e209c-186">Associe os perfis técnicos de conector aos perfis de hardware em **Varejo > Configuração de canal > Configuração do PDV > Perfis de PDV > Perfis de hardware**.</span><span class="sxs-lookup"><span data-stu-id="e209c-186">Bind the connector technical profiles to the hardware profiles in **Retail > Channel setup > POS setup > POS profiles > Hardware profiles**.</span></span>
   - <span data-ttu-id="e209c-187">Clique em **Editar**. Depois, clique em **Novo** na guia **Perfil técnico fiscal**.</span><span class="sxs-lookup"><span data-stu-id="e209c-187">Click **Edit**, then click **New** on the **Fiscal technical profile** tab.</span></span>
   - <span data-ttu-id="e209c-188">Selecione um perfil técnico de conector no campo **Número do perfil**.</span><span class="sxs-lookup"><span data-stu-id="e209c-188">Select a connector technical profile in the **Profile number** field.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="e209c-189">Você pode adicionar vários perfis técnicos a um perfil de hardware.</span><span class="sxs-lookup"><span data-stu-id="e209c-189">You can add several technical profiles to a hardware profile.</span></span> <span data-ttu-id="e209c-190">Entretanto, isso não é tem suporte se um perfil de hardware tem mais de uma interseção a qualquer grupo de conectores.</span><span class="sxs-lookup"><span data-stu-id="e209c-190">However, this is not supported if a hardware profile has more than one intersection with any connector group.</span></span> <span data-ttu-id="e209c-191">Para evitar configurações incorretas, é recomendável validar o processo de registro após atualizar todos os perfis de hardware.</span><span class="sxs-lookup"><span data-stu-id="e209c-191">To avoid incorrect settings, it’s recommended that you validate the registration process after updating all the hardware profiles.</span></span>

