---
title: Visão geral de assinaturas eletrônicas
description: Este artigo apresenta uma visão geral das assinaturas eletrônicas e descreve como usá-las.
author: maertenm
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d2e5144517a880c41cf04998ed53a826a75ecefb
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176504"
---
# <a name="electronic-signatures-overview"></a><span data-ttu-id="04920-103">Visão geral de assinaturas eletrônicas</span><span class="sxs-lookup"><span data-stu-id="04920-103">Electronic signatures overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04920-104">Este artigo apresenta uma visão geral das assinaturas eletrônicas e descreve como usá-las.</span><span class="sxs-lookup"><span data-stu-id="04920-104">This article provides an overview of electronic signatures and describes how they can be used.</span></span>

## <a name="what-is-an-electronic-signature"></a><span data-ttu-id="04920-105">O que é uma assinatura eletrônica?</span><span class="sxs-lookup"><span data-stu-id="04920-105">What is an electronic signature?</span></span>

<span data-ttu-id="04920-106">Uma assinatura eletrônica confirma a identidade de uma pessoa que está prestes a iniciar ou aprovar um processo de computação.</span><span class="sxs-lookup"><span data-stu-id="04920-106">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="04920-107">Em algumas indústrias, uma assinatura eletrônica tem o mesmo valor legal que a assinatura manuscrita.</span><span class="sxs-lookup"><span data-stu-id="04920-107">In some industries, an electronic signature is as legally binding as a handwritten signature.</span></span>

<span data-ttu-id="04920-108">As assinaturas eletrônicas são um requisito de regulamentações de conformidade para diversos setores regulamentados, como as indústrias farmacêutica, alimentícia, aeroespacial e de defesa.</span><span class="sxs-lookup"><span data-stu-id="04920-108">Electronic signatures are a regulations compliance requirement for several regulated industries, such as pharmaceuticals, food and beverage, and aerospace and defense.</span></span> <span data-ttu-id="04920-109">Também são necessárias para a conformidade com as regulamentações de 21 CFR Parte 11, emitidas pela FDA (agência de vigilância sanitária dos Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="04920-109">They are also required for compliance with regulations in 21 CFR Part 11 that was issued by the Food and Drug Administration (FDA) in the United States.</span></span>

> [!NOTE]
> <span data-ttu-id="04920-110">Uma assinatura eletrônica por si só não é o mesmo que uma assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="04920-110">An electronic signature by itself isn't the same as a digital signature.</span></span> <span data-ttu-id="04920-111">Uma assinatura eletrônica é simplesmente um substituto para uma assinatura manuscrita, ao passo que uma assinatura digital fornece medidas de segurança adicionais.</span><span class="sxs-lookup"><span data-stu-id="04920-111">An electronic signature is just a substitute for a handwritten signature, whereas a digital signature provides additional security measures.</span></span> <span data-ttu-id="04920-112">Uma assinatura digital pode ajudar a identificar se outro usuário ou processo adulterou os dados.</span><span class="sxs-lookup"><span data-stu-id="04920-112">A digital signature can help identify whether another user or process has tampered with the data.</span></span> <span data-ttu-id="04920-113">Uma assinatura digital também pode ser verificada e essa verificação não pode ser refutada pelo proprietário do certificado usado para assinar os dados.</span><span class="sxs-lookup"><span data-stu-id="04920-113">A digital signature can also be verified, and this verification can't be refuted by the owner of the certificate that was used to sign the data.</span></span> <span data-ttu-id="04920-114">Conforme descrito abaixo, as assinaturas eletrônicas têm a funcionalidade interna de assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="04920-114">As described below, electronic signatures have built-in digital signature functionality.</span></span>

## <a name="electronic-signatures"></a><span data-ttu-id="04920-115">Assinaturas eletrônicas</span><span class="sxs-lookup"><span data-stu-id="04920-115">Electronic signatures</span></span>

<span data-ttu-id="04920-116">Você pode usar assinaturas eletrônicas para processos comerciais críticos.</span><span class="sxs-lookup"><span data-stu-id="04920-116">You can use electronic signatures for critical business processes.</span></span> <span data-ttu-id="04920-117">Alguns processos têm recursos internos de assinatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="04920-117">Some processes have built-in electronic signature capabilities.</span></span> <span data-ttu-id="04920-118">Você também pode criar requisitos de assinatura personalizados para qualquer tabela e campo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="04920-118">You can also create custom signature requirements for any database table and field.</span></span>

<span data-ttu-id="04920-119">As assinaturas eletrônicas têm uma funcionalidade interna de assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="04920-119">Electronic signatures have built-in digital signature functionality.</span></span> <span data-ttu-id="04920-120">Cada usuário que assina documentos deve obter um certificado criptográfico válido.</span><span class="sxs-lookup"><span data-stu-id="04920-120">Every user who signs documents must obtain a valid cryptographic certificate.</span></span> <span data-ttu-id="04920-121">Quando um documento é assinado, a chave privada associada ao certificado é validada.</span><span class="sxs-lookup"><span data-stu-id="04920-121">When a document is signed, the private key that is associated with that certificate is validated.</span></span> <span data-ttu-id="04920-122">As informações de assinatura eletrônica são registradas em um log para fornecer uma trilha de auditoria.</span><span class="sxs-lookup"><span data-stu-id="04920-122">Electronic signature information is recorded in a log to provide an audit trail.</span></span> <span data-ttu-id="04920-123">Para configurar as assinaturas eletrônicas, consulte [Configurar assinaturas eletrônicas (Guia de tarefas)](tasks/set-up-electronic-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="04920-123">To set up electronic signatures, see [Set up electronic signatures (Task guide)](tasks/set-up-electronic-signatures.md).</span></span>

## <a name="users-who-require-access-to-electronic-signatures"></a><span data-ttu-id="04920-124">Usuários que precisam de acesso para assinaturas eletrônicas</span><span class="sxs-lookup"><span data-stu-id="04920-124">Users who require access to electronic signatures</span></span>

<span data-ttu-id="04920-125">Normalmente, três tipos de usuários requerem o acesso de segurança para assinaturas eletrônicas: administradores de assinatura eletrônica, signatários e auditores de assinatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="04920-125">Three kinds of users typically require security access to electronic signatures: electronic signature administrators, signers, and electronic signature auditors.</span></span>

### <a name="electronic-signature-administrator"></a><span data-ttu-id="04920-126">Administrador de assinatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="04920-126">Electronic signature administrator</span></span>

<span data-ttu-id="04920-127">O administrador de assinatura eletrônica configura os requisitos de assinatura, os parâmetros gerais e os aprovadores, além de receber alertas quando assinaturas não puderem ser verificadas.</span><span class="sxs-lookup"><span data-stu-id="04920-127">The electronic signature administrator sets up signature requirements, general parameters, and approvers, and receives alerts when signatures can't be verified.</span></span> <span data-ttu-id="04920-128">Por padrão, um usuário que pertence à função de segurança **Gerente de tecnologia da informação** tem permissão para administrar assinaturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="04920-128">By default, a user who belongs to the **Information technology manager** security role has permission to administer electronic signatures.</span></span>

### <a name="signer"></a><span data-ttu-id="04920-129">Signatário</span><span class="sxs-lookup"><span data-stu-id="04920-129">Signer</span></span>

<span data-ttu-id="04920-130">Um signatário fornece assinaturas eletrônicas para documentos e processos que exigem assinaturas.</span><span class="sxs-lookup"><span data-stu-id="04920-130">A signer provides electronic signatures for documents and processes that require signatures.</span></span> <span data-ttu-id="04920-131">Por padrão, um usuário que pertence à função de segurança **Usuário do sistema** tem permissão para assinar documentos eletronicamente.</span><span class="sxs-lookup"><span data-stu-id="04920-131">By default, a user who belongs to the **System user** security role has permission to sign documents electronically.</span></span>

> [!NOTE]
> <span data-ttu-id="04920-132">O signatário pode exigir permissões adicionais antes da concessão de acesso aos dados relacionados ao documento ou ao processo que está sendo assinado.</span><span class="sxs-lookup"><span data-stu-id="04920-132">The signer might require additional permissions before access is granted to data that is related to the document or process that is being signed.</span></span> <span data-ttu-id="04920-133">Um usuário que altera dados e, em seguida, deve assinar essas alterações, deve ter permissão para alterar os dados.</span><span class="sxs-lookup"><span data-stu-id="04920-133">A user who changes data and must then sign for those changes must have permission to change the data.</span></span> <span data-ttu-id="04920-134">Um usuário que assina em nome de outro usuário talvez não exija acesso aos dados.</span><span class="sxs-lookup"><span data-stu-id="04920-134">A user who signs on behalf of another user might not require access to the data.</span></span> <span data-ttu-id="04920-135">Um exemplo desse tipo de usuário é um supervisor que assina alterações de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="04920-135">An example of this kind of user is a supervisor who signs for an employee's changes.</span></span>

### <a name="electronic-signature-auditor"></a><span data-ttu-id="04920-136">Auditor de assinatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="04920-136">Electronic signature auditor</span></span>

<span data-ttu-id="04920-137">O auditor de assinatura eletrônica revisa o log do banco de dados e o log de revisão de assinatura disponível no log do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="04920-137">The electronic signature auditor reviews the database log and the signature review log that is available from the database log.</span></span> <span data-ttu-id="04920-138">Por padrão, um usuário que pertence à função de segurança **Gerente de tecnologia da informação** tem permissão para auditar assinaturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="04920-138">By default, a user who belongs to the **Information technology manager** security role has permission to audit electronic signatures.</span></span>

<span data-ttu-id="04920-139">Se você usar uma função diferente de **Gerente de tecnologia da informação**, certifique-se de que a função foi atribuída aos seguintes privilégios:</span><span class="sxs-lookup"><span data-stu-id="04920-139">If you use a role other than **Information technology manager**, make sure that the role is assigned the following privileges:</span></span>

- <span data-ttu-id="04920-140">Exibir falhas de assinatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="04920-140">View electronic signature failures</span></span>
- <span data-ttu-id="04920-141">Exibir log do banco de dados</span><span class="sxs-lookup"><span data-stu-id="04920-141">View database log</span></span>

## <a name="signing-documents-electronically"></a><span data-ttu-id="04920-142">Assinando documentos eletronicamente</span><span class="sxs-lookup"><span data-stu-id="04920-142">Signing documents electronically</span></span>

### <a name="get-a-certificate"></a><span data-ttu-id="04920-143">Obter um certificado</span><span class="sxs-lookup"><span data-stu-id="04920-143">Get a certificate</span></span>

<span data-ttu-id="04920-144">Antes de assinar documentos eletronicamente, você deve solicitar um certificado.</span><span class="sxs-lookup"><span data-stu-id="04920-144">Before you sign documents electronically, you must request a certificate.</span></span>

> [!NOTE]
> <span data-ttu-id="04920-145">O recursos do Microsoft SQL Server são usados para criar certificados e habilitar a assinatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="04920-145">Microsoft SQL Server features are used to create certificates and enable electronic signing.</span></span> <span data-ttu-id="04920-146">Nenhuma infraestrutura de certificado ou de chave pública adicional (PKI) é necessária.</span><span class="sxs-lookup"><span data-stu-id="04920-146">No additional certificate or public key infrastructure (PKI) is required.</span></span>

<span data-ttu-id="04920-147">Ao solicitar um certificado, uma chave pública e uma chave privada são criadas para você.</span><span class="sxs-lookup"><span data-stu-id="04920-147">When you request a certificate, a public key and a private key are created for you.</span></span> <span data-ttu-id="04920-148">A chave privada é criptografada usando uma senha que apenas você sabe.</span><span class="sxs-lookup"><span data-stu-id="04920-148">The private key is encrypted by using a password that is known only to you.</span></span> <span data-ttu-id="04920-149">Ao assinar um documento eletronicamente, sua identidade é verificada quando você insere a senha.</span><span class="sxs-lookup"><span data-stu-id="04920-149">When you sign a document electronically, your identity is verified when you enter the password.</span></span>

<span data-ttu-id="04920-150">Para solicitar um certificado, na página **Opções**, na guia **Contas**, clique em **Adquirir certificado**.</span><span class="sxs-lookup"><span data-stu-id="04920-150">To request a certificate, on the **Options** page, on the **Accounts** tab, click **Get certificate**.</span></span>

<span data-ttu-id="04920-151">Você deve digitar e confirmar a senha usada para assinar.</span><span class="sxs-lookup"><span data-stu-id="04920-151">You must enter and confirm the password that you will use for signing.</span></span> <span data-ttu-id="04920-152">A senha será usada para proteger a chave privada e autorizar o uso do certificado.</span><span class="sxs-lookup"><span data-stu-id="04920-152">The password is used to protect your private key and authorize the use of your certificate.</span></span> <span data-ttu-id="04920-153">Essa senha não fica armazenada no banco de dados e não está disponível para mais ninguém, nem mesmo o administrador.</span><span class="sxs-lookup"><span data-stu-id="04920-153">This password isn't stored in the database, and it isn't available to anyone else, not even to the administrator.</span></span>

<span data-ttu-id="04920-154">Se você esquecer a senha associada ao certificado, ela deverá ser redefinida.</span><span class="sxs-lookup"><span data-stu-id="04920-154">If you forget the password that is connected with your certificate, that certificate must be reset.</span></span> <span data-ttu-id="04920-155">A redefinição do certificado não afeta os documentos assinados com o certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="04920-155">If you reset the certificate, you don't affect documents that you signed by using the previous certificate.</span></span> <span data-ttu-id="04920-156">Para redefinir o certificado na página **Opções**, clique em **Redefinir certificado**.</span><span class="sxs-lookup"><span data-stu-id="04920-156">To reset the certificate, on the **Options** page, click **Reset certificate**.</span></span>

### <a name="sign-a-document-electronically"></a><span data-ttu-id="04920-157">Assinar um documento eletronicamente</span><span class="sxs-lookup"><span data-stu-id="04920-157">Sign a document electronically</span></span>

<span data-ttu-id="04920-158">A página **Assinar documento** é exibida quando você faz uma alteração que requer um assinatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="04920-158">The **Sign document** page is displayed when you make a change that requires an electronic signature.</span></span>

1. <span data-ttu-id="04920-159">Na página **Atribuir documento**, clique na guia **Documento** para revisar as alterações do documento.</span><span class="sxs-lookup"><span data-stu-id="04920-159">On the **Sign document** page, click the **Document** tab to review the changes to the document.</span></span>
2. <span data-ttu-id="04920-160">Na guia **Assinatura**, selecione um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="04920-160">On the **Signature** tab, select a reason code.</span></span>
3. <span data-ttu-id="04920-161">Insira um comentário, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="04920-161">Enter a comment, if a comment is required.</span></span>
4. <span data-ttu-id="04920-162">Se a sua ID de usuário não for exibida no campo **Signatário**, selecione-a na lista.</span><span class="sxs-lookup"><span data-stu-id="04920-162">If your user ID doesn't appear in the **Signer** field, select it in the list.</span></span>
5. <span data-ttu-id="04920-163">Insira sua localização, se essa informação for necessária.</span><span class="sxs-lookup"><span data-stu-id="04920-163">Enter your location, if this information is required.</span></span>
6. <span data-ttu-id="04920-164">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="04920-164">Click **OK**.</span></span>

### <a name="sign-for-another-users-changes"></a><span data-ttu-id="04920-165">Assinar alterações de outro usuário</span><span class="sxs-lookup"><span data-stu-id="04920-165">Sign for another user's changes</span></span>

<span data-ttu-id="04920-166">É possível que às vezes você deseje que um usuário assine as alterações de outro.</span><span class="sxs-lookup"><span data-stu-id="04920-166">Occasionally, you might want a user to sign for another user's changes.</span></span> <span data-ttu-id="04920-167">Por exemplo, um supervisor pode ser responsável por assinar as alterações que um funcionário faz em uma lista de materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="04920-167">For example, a supervisor might be required to sign for changes that an employee makes to a bill of materials (BOM).</span></span> <span data-ttu-id="04920-168">Use este procedimento para designar um usuário como signatário de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="04920-168">Use this procedure to designate a user as a signer for another user.</span></span>

> [!NOTE]
> <span data-ttu-id="04920-169">Quando um usuário assina a alteração de outro usuário, a assinatura deve ser fornecida na estação de trabalho do usuário que fez a alteração.</span><span class="sxs-lookup"><span data-stu-id="04920-169">When one user signs for another user's change, the signature must be provided at the workstation of the user who made the change.</span></span> <span data-ttu-id="04920-170">O usuário não pode salvar a alteração até que a assinatura seja fornecida.</span><span class="sxs-lookup"><span data-stu-id="04920-170">The user can't save the change until the signature has been provided.</span></span>

<span data-ttu-id="04920-171">Para designar aprovadores, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="04920-171">To designate approvers, follow these steps.</span></span>

1. <span data-ttu-id="04920-172">Na página **Opções**, na guia **Contas**, clique em **Designar aprovação**.</span><span class="sxs-lookup"><span data-stu-id="04920-172">On the **Options** page, on the **Accounts** tab, click **Designate approver**.</span></span>
2. <span data-ttu-id="04920-173">No campo **ID de usuário aprovador**, selecione a ID do usuário que deve assinar as alterações de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="04920-173">In the **Approver user ID** field, select the ID of the user who must sign for another user's changes.</span></span>
3. <span data-ttu-id="04920-174">No campo **Atribuir para ID de usuário**, selecione a ID do usuário cujas alterações devem ser assinadas.</span><span class="sxs-lookup"><span data-stu-id="04920-174">In the **Sign for user ID** field, select the ID of the user whose changes must be signed for.</span></span>
