---
title: Definir mensagens eletrônicas para eventos do SPED-Reinf
description: Este tópico explica como configurar mensagens eletrônicas para eventos SPED-Reinf para o Brasil.
author: sndray
ms.date: 04/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: de5d5a02869baf10c831ebdc9034a4e7c9f89b2c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020077"
---
# <a name="set-up-electronic-messages-for-sped-reinf-events"></a><span data-ttu-id="3ac9c-103">Definir mensagens eletrônicas para eventos do SPED-Reinf</span><span class="sxs-lookup"><span data-stu-id="3ac9c-103">Set up electronic messages for SPED-Reinf events</span></span>

<span data-ttu-id="3ac9c-104">A funcionalidade de mensagens eletrônicas é nova no Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-104">Electronic message functionality is new in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="3ac9c-105">Ela permite manter e acompanhar vários processos de mensagens eletrônicas quando há uma troca de informações entre o Finance e os serviços Web da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-105">It lets you maintain and track various processes for electronic messages when there is an exchange of information between Finance and tax authority web services.</span></span>

<span data-ttu-id="3ac9c-106">Antes de emitir eventos SPED-Reinf para o site do governo, use a configuração predefinida que a Microsoft preparou para atender aos requisitos SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-106">Before you issue SPED-Reinf events to the government website, use the predefined configuration that Microsoft has prepared to meet SPED-Reinf requirements.</span></span> <span data-ttu-id="3ac9c-107">Essa configuração é fornecida como uma entidade de dados.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-107">This configuration is delivered as a data entity.</span></span> <span data-ttu-id="3ac9c-108">Quando ele for importado para o Finance, os usuários poderão gerar, validar e fornecer todos os eventos que são descritos no escopo do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-108">After it's imported into Finance, users will be able to generate, validate, and deliver all events that are described in the SPED-Reinf scope.</span></span>

## <a name="import-the-configuration-from-the-data-entity"></a><span data-ttu-id="3ac9c-109">Importar a configuração da entidade de dados</span><span class="sxs-lookup"><span data-stu-id="3ac9c-109">Import the configuration from the data entity</span></span>

<span data-ttu-id="3ac9c-110">Para configurar a funcionalidade de mensagem eletrônica para a comunicação de eventos do SPED-Reinf, use a configuração predefinida disponível no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="3ac9c-110">To set up electronic message functionality for communication of SPED-Reinf events, use the predefined configuration that is available in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="3ac9c-111">Entre no [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="3ac9c-111">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
2. <span data-ttu-id="3ac9c-112">Selecione o bloco **Biblioteca compartilhada de ativos**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-112">Select the **Shared asset library** tile.</span></span>
3. <span data-ttu-id="3ac9c-113">Selecione **Pacote de dados** como o tipo de ativo e selecione o pacote para as entidades de dados de comunicação do evento do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-113">Select **Data package** as the asset type, and then select the package for the SPED-Reinf event communication data entities.</span></span> <span data-ttu-id="3ac9c-114">(O nome do arquivo é **SPEDReinf_EMSettings.zip**.)</span><span class="sxs-lookup"><span data-stu-id="3ac9c-114">(The file name is **SPEDReinf_EMSettings.zip**.)</span></span>
4. <span data-ttu-id="3ac9c-115">Salve o arquivo no local em que as entidades de dados devem ser armazenadas.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-115">Save the file in the location where data entities should be stored.</span></span>
5. <span data-ttu-id="3ac9c-116">Entre no Finance e vá para **Espaços de trabalho** \> **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-116">Sign in to Finance, and go to **Workspaces** \> **Data management**.</span></span>
6. <span data-ttu-id="3ac9c-117">Selecione o bloco **Importação**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-117">Select the **Import** tile.</span></span>
7. <span data-ttu-id="3ac9c-118">Insira uma descrição e um nome para identificar o trabalho, como **SpedReinf**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-118">Enter a description and a name to identify the job, such as **SpedReinf**.</span></span>
8. <span data-ttu-id="3ac9c-119">No campo **Formato de dados de origem**, selecione **Pacote**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-119">In the **Source data format** field, select **Package**.</span></span>
9. <span data-ttu-id="3ac9c-120">Selecione **Carregar** e, em seguida, selecione o arquivo que você salvou do LCS (**SPEDReinf_EMSettings.zip**).</span><span class="sxs-lookup"><span data-stu-id="3ac9c-120">Select **Upload**, and then select the file that you saved from LCS (**SPEDReinf_EMSettings.zip**).</span></span>
10. <span data-ttu-id="3ac9c-121">Selecione **Salvar** e aguarde até que todas as entidades de dados sejam mostradas na página.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-121">Select **Save**, and wait until all data entities are shown on the page.</span></span>
11. <span data-ttu-id="3ac9c-122">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-122">Select **Import**.</span></span>

    <span data-ttu-id="3ac9c-123">Você receberá uma notificação sobre o processo de importação.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-123">You will receive a notification about the import process.</span></span> <span data-ttu-id="3ac9c-124">Você também pode atualizar a página manualmente para visualizar o progresso do processo de importação.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-124">You can also manually refresh the page to view the progress of the import process.</span></span> <span data-ttu-id="3ac9c-125">Quando o processo for concluído, você poderá visualizar a página **Resumo de execução**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-125">When the process is completed, you can view the **Execution summary** page.</span></span>

    ![Página Resumo de execução](media/bra-execution-summary-page.png)

## <a name="structure-of-electronic-messages"></a><span data-ttu-id="3ac9c-127">Estrutura de mensagens eletrônicas</span><span class="sxs-lookup"><span data-stu-id="3ac9c-127">Structure of electronic messages</span></span>

<span data-ttu-id="3ac9c-128">Cada evento criado, entregue e recebido é representado por uma mensagem e um item de mensagem.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-128">Every event that is created, delivered, and received is represented by a message and a message item.</span></span>

![Estrutura de mensagens eletrônicas](media/bra-electronic-messages-structure.png)

<span data-ttu-id="3ac9c-130">O item de mensagem é representado pela mensagem do evento XLM.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-130">The message item is represented by the XML event message.</span></span> <span data-ttu-id="3ac9c-131">Isso inclui as seguintes informações que são armazenadas na mensagem ou atualizada no Finance:</span><span class="sxs-lookup"><span data-stu-id="3ac9c-131">It includes the following information that is stored in the message or updated in Finance:</span></span>

- <span data-ttu-id="3ac9c-132">O número completo do CNPJ (Cadastro Nacional de Pessoas Jurídicas) do estabelecimento fiscal</span><span class="sxs-lookup"><span data-stu-id="3ac9c-132">The full National Registry of Legal Entities (CNPJ) number of the fiscal establishment</span></span>
- <span data-ttu-id="3ac9c-133">O CNPJ raiz</span><span class="sxs-lookup"><span data-stu-id="3ac9c-133">The root CNPJ</span></span>
- <span data-ttu-id="3ac9c-134">O período de escrituração</span><span class="sxs-lookup"><span data-stu-id="3ac9c-134">The booking period</span></span>
- <span data-ttu-id="3ac9c-135">A data inicial do período para o qual a mensagem é válida</span><span class="sxs-lookup"><span data-stu-id="3ac9c-135">The start date of the period that the message is valid for</span></span>
- <span data-ttu-id="3ac9c-136">O número do protocolo de recebimento</span><span class="sxs-lookup"><span data-stu-id="3ac9c-136">The receipt protocol number</span></span>
- <span data-ttu-id="3ac9c-137">Um valor que indica se a mensagem está registrada no Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3ac9c-137">A value that indicates whether the message is registered in Dynamics 365</span></span>

<span data-ttu-id="3ac9c-138">Você pode encontrar esta configuração na página **Campos adicionais** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Campos adicionais**).</span><span class="sxs-lookup"><span data-stu-id="3ac9c-138">You can find this configuration on the **Additional fields** page (**Tax** \> **Setup** \> **Electronic messages** \> **Additional fields**).</span></span>

![Configuração na página Campos adicionais](media/bra-electronic-messaging-additional-fields.png)

> [!NOTE]
> <span data-ttu-id="3ac9c-140">Não remova esta configuração.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-140">Don't remove this configuration.</span></span> <span data-ttu-id="3ac9c-141">Essa configuração está incluída no pacote.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-141">This configuration is included in the package.</span></span>

<span data-ttu-id="3ac9c-142">Os tipos de item de mensagem são classificados pelo tipo de evento na página **Tipos de item de mensagem** (**Imposto** \> **Configuração** \> **Mensagem eletrônica** \> **Tipos de item de mensagem**).</span><span class="sxs-lookup"><span data-stu-id="3ac9c-142">The message item types are classified by the type of event on the **Message item types** page (**Tax** \> **Setup** \> **Electronic messages** \> **Message item types**).</span></span>

![Página Tipos de item de mensagem](media/bra-message-types.png)

> [!NOTE]
> <span data-ttu-id="3ac9c-144">Não remova esta configuração.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-144">Don't remove this configuration.</span></span> <span data-ttu-id="3ac9c-145">Essa configuração está incluída no pacote.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-145">This configuration is included in the package.</span></span>

- <span data-ttu-id="3ac9c-146">Para configurar a sequência numérica para itens de mensagem, acesse **Imposto \> Configuração \> Parâmetros \> Parâmetros do razão geral** e, na guia **Sequências numéricas**, selecione uma sequência numérica para as referências **Mensagem** e **Item de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-146">To set up the number sequence for message items, go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Number sequences** tab, select a number sequence for the **Message** and **Message item** references.</span></span>

![Guia Sequências numéricas na página Parâmetros do razão geral](media/bra-electronic-messages-number-sequences.png)

> [!NOTE]
> <span data-ttu-id="3ac9c-148">A sequência numérica deve ser definida como não contínua.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-148">The number sequence must be defined as non-continuous.</span></span>

## <a name="certificates"></a><span data-ttu-id="3ac9c-149">Certificados</span><span class="sxs-lookup"><span data-stu-id="3ac9c-149">Certificates</span></span>

<span data-ttu-id="3ac9c-150">Os certificados confiáveis devem ser configurados e usados no Finance, pois o SPED-Reinf deve sempre ser assinado por um certificado de e-CNPJ que seja autorizado pela Infraestrutura de Chave Pública do Brasil (ICP-Brasil), independentemente de outras assinaturas.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-150">Trusted certificates must be configured and used in Finance, because the SPED-Reinf should always be signed by an e-CNPJ certificate that is authorized by the Brazilian Public Key Infrastructure (ICP-Brasil), regardless of any other signatures.</span></span> <span data-ttu-id="3ac9c-151">Este certificado de e-CNPJ deve corresponder aos oito primeiros dígitos do número de CNPJ do estabelecimento fiscal raiz, pois o relatório é emitido pelo estabelecimento fiscal raiz e os estabelecimentos fiscais relacionados.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-151">This e-CNPJ certificate should match the first eight digits of the root fiscal establishment's CNPJ number, because the report is issued by the root fiscal establishment and the related fiscal establishments.</span></span>

<span data-ttu-id="3ac9c-152">No Finance, você deve registrar o certificado do Key Vault no Azure.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-152">In Finance, you must register the Key Vault certificate in Azure.</span></span>

<span data-ttu-id="3ac9c-153">Para obter informações sobre como configurar um cliente do Key Vault, consulte [Configuração do Cliente do Azure Key Vault](https://support.microsoft.com/help/4040305).</span><span class="sxs-lookup"><span data-stu-id="3ac9c-153">For information about how to set up a Key Vault client, see [Setting up Azure Key Vault Client](https://support.microsoft.com/help/4040305).</span></span>

1. <span data-ttu-id="3ac9c-154">Vá para **Administração do sistema** \> **Configuração** \> **Parâmetros do Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-154">Go to **System administration** \> **Setup** \> **Key Vault parameters**.</span></span>
2. <span data-ttu-id="3ac9c-155">Digite as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3ac9c-155">Enter the following information:</span></span>

    - <span data-ttu-id="3ac9c-156">URL do Key Vault</span><span class="sxs-lookup"><span data-stu-id="3ac9c-156">Key Vault URL</span></span>
    - <span data-ttu-id="3ac9c-157">Cliente do Key Vault</span><span class="sxs-lookup"><span data-stu-id="3ac9c-157">Key Vault client</span></span>
    - <span data-ttu-id="3ac9c-158">Chave secreta do Key Vault</span><span class="sxs-lookup"><span data-stu-id="3ac9c-158">Key Vault secret key</span></span>
    - <span data-ttu-id="3ac9c-159">ID secreto do Key Vault</span><span class="sxs-lookup"><span data-stu-id="3ac9c-159">Key Vault secret ID</span></span>

<span data-ttu-id="3ac9c-160">Após o registro, associe o certificado nos parâmetros de configuração para a ação **Geração de relatório**, conforme descrito na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-160">After registration, associate the certificate in the setup parameters for the **Report generation** action, as described in the next section.</span></span>

## <a name="set-up-parameters"></a><span data-ttu-id="3ac9c-161">Configurar parâmetros</span><span class="sxs-lookup"><span data-stu-id="3ac9c-161">Set up parameters</span></span> 

<span data-ttu-id="3ac9c-162">Sempre que uma mensagem é criada, preparada, validada, entregue ou recebida, a ação relacionada deve ser identificada por meio de uma classe X++ na página **Configurações de classe executável** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Configurações de classe executável**).</span><span class="sxs-lookup"><span data-stu-id="3ac9c-162">Every time that a message is created, prepared, validated, delivered, or received, the related action must be identified through an X++ class on the **Executable class settings** page (**Tax** \> **Setup** \> **Electronic messages** \> **Executable class settings**).</span></span>

- <span data-ttu-id="3ac9c-163">**Preparação dos eventos –** Esta ação é usada para criar e preparar a mensagem XML.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-163">**Preparation items (Preparacao dos eventos)** – This action is used to create and prepare the XML message.</span></span> <span data-ttu-id="3ac9c-164">Esta ação solicita mais parâmetros, tais como **Data da reserva**, **CNPJ** e **CNPJ raiz**, pois os eventos são gerados com base nessas informações.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-164">The action requests more parameters, such as **Booking date**, **CNPJ**, and **CNPJ root**, because the events are generated based on this information.</span></span>

    ![Parâmetros de itens de preparação](media/bra-preparation-items.png)

- <span data-ttu-id="3ac9c-166">**Resposta do processo** - Esta ação é usada para atualizar a mensagem entregue quando o governo a aprova usando um número de protocolo.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-166">**Process response (Processo de reposta)** – This action is used to update the delivered message when the government approves it by using a protocol number.</span></span> <span data-ttu-id="3ac9c-167">Além disso, a mensagem é atualizada como registrada no site do governo.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-167">Additionally, the message is updated as registered on the government website.</span></span>

    ![Parâmetros de resposta do processo de itens de preparação](media/bra-preparation-items-process-response.png)

- <span data-ttu-id="3ac9c-169">**Geração de relatório** – Esta ação é usada para enviar e receber o item de mensagem.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-169">**Report generation (Geracao de relatório)** – This action is used to send and receive the message item.</span></span>

    ![Gerar parâmetros de relatórios](media/bra-generate-reports-parameters.png)

> [!NOTE]
> <span data-ttu-id="3ac9c-171">Não remova esta configuração.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-171">Don't remove this configuration.</span></span> <span data-ttu-id="3ac9c-172">Essa configuração está incluída no pacote.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-172">This configuration is included in the package.</span></span>

## <a name="specific-actions"></a><span data-ttu-id="3ac9c-173">Ações específicas</span><span class="sxs-lookup"><span data-stu-id="3ac9c-173">Specific actions</span></span>

<span data-ttu-id="3ac9c-174">Antes de uma mensagem ser entregue, configure a validação do esquema XML para ajudar a evitar rejeições por parte do site do governo.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-174">Before a message is delivered, set up XML schema validation to help prevent rejections from the government website.</span></span>

1. <span data-ttu-id="3ac9c-175">Vá para **Administração da organização** \> **Gerenciamento de documentos** \> **Parâmetros de gerenciamento de documentos** e habilite arquivos .xsd adicionando **XSD** como um novo tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-175">Go to **Organization administration** \> **Document management** \> **Document management parameters**, and enable .xsd files by adding **XSD** as a new file type.</span></span>

    ![Página Parâmetros de gerenciamento de documentos](media/bra-document-management-parameters.png)

2. <span data-ttu-id="3ac9c-177">Vá para **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de processamento de mensagem** e selecione **Novo** \> **Arquivo** para anexar os esquemas (arquivos .xsd) às seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="3ac9c-177">Go to **Tax** \> **Setup** \> **Electronic messages** \> **Message processing actions**, and select **New** \> **File** to attach the schemas (.xsd files) to the following actions:</span></span>

    - <span data-ttu-id="3ac9c-178">Validar</span><span class="sxs-lookup"><span data-stu-id="3ac9c-178">Verify (Validar)</span></span>
    - <span data-ttu-id="3ac9c-179">Re-Validar</span><span class="sxs-lookup"><span data-stu-id="3ac9c-179">Re-Verify (Re-Validar)</span></span>
    - <span data-ttu-id="3ac9c-180">Exclusão-Validar</span><span class="sxs-lookup"><span data-stu-id="3ac9c-180">Cancel-Verify (Exclusão-Validar)</span></span>

3. <span data-ttu-id="3ac9c-181">Vá para **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de processamento de mensagem**, selecione a ação **Preencher** (**Incluir**) e, no campo **Preencher ação de registro**, selecione **Registrar transacões**.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-181">Go to **Tax** \> **Setup** \> **Electronic messages** \> **Message processing actions**, select the **Populate** (**Incluir**) action, and then, in the **Populate records action** field, select **Registrar transacões**.</span></span>

    ![Página Ações de processamento de mensagem](media/bra-message-processing-actions.png)

4. <span data-ttu-id="3ac9c-183">Vá para **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Configurações de serviços Web** e configure uma conexão de serviços Web e certificados para emitir e consultar eventos.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-183">Go to **Tax** \> **Setup** \> **Electronic messages** \> **Web service settings**, and set up a web services connection and certificates for issuing and inquiring about events.</span></span>

    ![Página Configurações de serviços Web](media/bra-web-service-settings.png)

> [!NOTE]
> <span data-ttu-id="3ac9c-185">Nas configurações do **SPED Reinf assíncrono**, inclua o endereço do serviço Web para consultar o evento R-5011.</span><span class="sxs-lookup"><span data-stu-id="3ac9c-185">In the settings for **SPED Reinf asynchronous (SPED Reinf – assíncrono)**, include the web service address for inquire event R-5011.</span></span>
