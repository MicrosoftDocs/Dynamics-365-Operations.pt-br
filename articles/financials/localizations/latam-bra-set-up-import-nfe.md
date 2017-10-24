---
title: Configurar, importar e verificar documentos XML de NF-e e de DANFE
description: "Você pode extrair e importar automaticamente o XML da Nota fiscal Eletrônica (NF-e) e seu DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) de e-mails enviados pelo fornecedor de sua empresa."
author: v-gonode
manager: AnnBe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Brazil
ms.author: v-gonode
ms.search.validFrom: 
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cdf2c32d97410579eed1cccdd76831431c33bf13
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-import-and-verify-nf-e-xml-documents-and-danfe"></a><span data-ttu-id="ca575-103">Configurar, importar e verificar documentos XML de NF-e e de DANFE</span><span class="sxs-lookup"><span data-stu-id="ca575-103">Set up, import, and verify NF-e XML documents and DANFE</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ca575-104">Você pode extrair e importar automaticamente o XML da Nota fiscal Eletrônica (NF-e) e seu DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) de e-mails enviados pelo fornecedor de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ca575-104">You can automatically extract and import the XML from the Nota Fiscal Eletrônica (NF-e) and its DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) from emails sent by the vendor for your company.</span></span> <span data-ttu-id="ca575-105">O fornecedor deve enviar esses emails como anexos durante o período no qual as mercadorias adquiridas estão em trânsito.</span><span class="sxs-lookup"><span data-stu-id="ca575-105">The vendor must send these emails as file attachements during the time which the acquired goods are in transit.</span></span>

<span data-ttu-id="ca575-106">Os seguintes pré-requisitos devem ser atendidos antes de você começar:</span><span class="sxs-lookup"><span data-stu-id="ca575-106">The following prerequisites must be in place before you begin:</span></span> 
 - <span data-ttu-id="ca575-107">Configurar estabelecimentos fiscais na entidade legal.</span><span class="sxs-lookup"><span data-stu-id="ca575-107">Configure fiscal establishments in your legal entity.</span></span> 
 - <span data-ttu-id="ca575-108">Configurar parâmetros federais de NF-e, incluindo o código de IBGE selecionado nos parâmetros da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="ca575-108">Set up NF-e federal parameters, including the IBGE code selected in the tax authority parameters.</span></span>
 - <span data-ttu-id="ca575-109">Configurar parâmetros de NF-e para estabelecimentos fiscais.</span><span class="sxs-lookup"><span data-stu-id="ca575-109">Set up NF-e parameters for fiscal establishments.</span></span>

## <a name="set-up-email-accounts-to-import-xml-files-and-danfe-for-nf-e"></a><span data-ttu-id="ca575-110">Configurar contas de e-mail para importar arquivos XML e DANFE para a NF-e</span><span class="sxs-lookup"><span data-stu-id="ca575-110">Set up email accounts to import XML files and DANFE for NF-e</span></span>
- <span data-ttu-id="ca575-111">Na página **Configurar contas de email**, clique em **Novo** e insira os detalhes da conta.</span><span class="sxs-lookup"><span data-stu-id="ca575-111">On the **Configure email accounts** page, click **New** and enter the account details.</span></span>
   - <span data-ttu-id="ca575-112">**Endereço do servidor** - Insira o endereço do servidor POP3 para a conta de email.</span><span class="sxs-lookup"><span data-stu-id="ca575-112">**Server address** - Enter the POP3 server address for the email account.</span></span>
   - <span data-ttu-id="ca575-113">**Porta** - Insira o número da porta a ser usado para o servidor de e-mail.</span><span class="sxs-lookup"><span data-stu-id="ca575-113">**Port** - Enter the port number to use for the email server.</span></span>
   - <span data-ttu-id="ca575-114">**SSL Necessário** - Marque esta opção para indicar que o servidor requer uma conexão criptografada de (SSL) Secure Socket Layer.</span><span class="sxs-lookup"><span data-stu-id="ca575-114">**Required SSL** - Select this option to indicate that the server requires a Secure Socket Layer (SSL) encrypted connection.</span></span>
   - <span data-ttu-id="ca575-115">**Nome de usuário** - Insira o nome do usuário para a conta de e-mail.</span><span class="sxs-lookup"><span data-stu-id="ca575-115">**Username** - Enter the user name for the email account.</span></span>
   - <span data-ttu-id="ca575-116">**Senha** - Insira a senha da conta de e-mail.</span><span class="sxs-lookup"><span data-stu-id="ca575-116">**Password** - Enter the password for the email account.</span></span>

## <a name="import-and-verify-the-nf-e-xml-files-and-danfe-from-emails"></a><span data-ttu-id="ca575-117">Importar e verificar os arquivos XML de NF-e e DANFE de e-mails</span><span class="sxs-lookup"><span data-stu-id="ca575-117">Import and verify the NF-e XML files and DANFE from emails</span></span>
1. <span data-ttu-id="ca575-118">Na página **Importar arquivos XML de email**, se necessário, insira parâmetros, as recorrências, e a agenda de processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="ca575-118">On the **Import XML files from email** page, if necessary, enter the batch processing parameters, recurrences, and schedule.</span></span>
2. <span data-ttu-id="ca575-119">Clique em **OK** para importar o XML e os arquivos de DANFE de email recebidos na conta de email.</span><span class="sxs-lookup"><span data-stu-id="ca575-119">Click **OK** to import the XML and the DANFE files from the emails received in the email account.</span></span>

<span data-ttu-id="ca575-120">Os arquivos XML e DANFE importados podem ser exibidos na página **Documentos XML recebidos de NF-e**.</span><span class="sxs-lookup"><span data-stu-id="ca575-120">The imported XML and DANFE files can be viewed on the **Received NF-e XML documents** page.</span></span>
> [!NOTE] 
> <span data-ttu-id="ca575-121">Somente o XML de Notas Fiscais Eletrônicas (NF-e) emitido para o CNPJ de estabelecimentos fiscais são importados dos emails.</span><span class="sxs-lookup"><span data-stu-id="ca575-121">Only the XML from Notas Fiscais Eletrônicas (NF-e) issued for the CNPJ of the fiscal establishments are imported from the emails.</span></span>

> [!NOTE] 
> <span data-ttu-id="ca575-122">O nome do emissor da Nota fiscal Eletrônica (NF-e) foi deixado em branco quando a ID de registro de impostos (CNPJ) não pode ser encontrada como um atributo de um fornecedor na página **Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="ca575-122">The name of the issuer of the Nota Fiscal Eletrônica (NF-e) is left blank when the tax registration ID (CNPJ) cannot be found as an attribute of a vendor in the **All vendors** page.</span></span>

 - <span data-ttu-id="ca575-123">Para uma Nota fiscal Eletrônica (NF-e) selecionada, clique em **Documento XML** para exibir o documento XML.</span><span class="sxs-lookup"><span data-stu-id="ca575-123">For a selected Nota Fiscal Eletrônica (NF-e), click **XML document** to view the XML document.</span></span>
 - <span data-ttu-id="ca575-124">Para uma Nota Fiscal Eletrônica (NF-e) selecionada, clique em **DANFE** para exibir o Documento Auxiliar da Nota Fiscal Eletrônica (DANFE).</span><span class="sxs-lookup"><span data-stu-id="ca575-124">For a selected Nota Fiscal Eletrônica (NF-e), click **DANFE** to view the Documento Auxiliar da Nota Fiscal Eletrônica (DANFE).</span></span>
 - <span data-ttu-id="ca575-125">Para uma Nota fiscal Eletrônica selecionada (NF-e), clique em **Consultar status** para consultar o status da NF-e na SEFAZ usando a chave de acesso.</span><span class="sxs-lookup"><span data-stu-id="ca575-125">For a selected Nota Fiscal Eletrônica (NF-e), click **Inquire status** to inquire on the status of the NF-e at the SEFAZ using the access key.</span></span>
> [!NOTE] 
> <span data-ttu-id="ca575-126">O status, a data, e as horas da consulta são atualizados no Status da SEFAZ e data e hora da última consulta.</span><span class="sxs-lookup"><span data-stu-id="ca575-126">The status, date, and time of the inquiry are updated in the Status from SEFAZ and Date and time from the last inquiry.</span></span>

## <a name="inquire-about-the-status-of-nf-e-access-keys-at-the-sefaz"></a><span data-ttu-id="ca575-127">Pesquisa sobre o status das teclas de acesso de NF-e no SEFAZ</span><span class="sxs-lookup"><span data-stu-id="ca575-127">Inquire about the status of NF-e access keys at the SEFAZ</span></span>
1. <span data-ttu-id="ca575-128">Na página **Consultar status da chave de acesso da NF-e**, no campo **Limite de cancelamento**, insira o número de horas que o fornecedor tem para cancelar a NF-e.</span><span class="sxs-lookup"><span data-stu-id="ca575-128">On the **Inquire about NF-e access key status** page, in the **Limit of cancellation** field, enter the number of hours that the vendor has to cancel the NF-e.</span></span>
2. <span data-ttu-id="ca575-129">No campo **Intervalo mínimo entre as consultas**, insira o intervalo mínimo entre as consultas em minutos da chave de acesso de NF-e recebida na SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="ca575-129">In the **Minimum inquiry interval** field, enter the minimum interval between the inquiries in minutes for the received NF-e access key at the SEFAZ.</span></span>
3. <span data-ttu-id="ca575-130">Se necessário, insira os parâmetros de processamento em lotes, as recorrências e a agenda.</span><span class="sxs-lookup"><span data-stu-id="ca575-130">If necessary, enter the batch processing parameters, recurrences, and schedule.</span></span>

