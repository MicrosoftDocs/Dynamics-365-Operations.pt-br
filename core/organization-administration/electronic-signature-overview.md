---
title: "Visão geral das assinaturas eletrônicas"
description: "Este artigo oferece uma visão geral de assinaturas eletrônicas e descreve como elas podem ser usadas no Microsoft Dynamics 365 for Finance and Operations."
author: maertenm
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 0cebd30a560ff033efab89c2055827b62cf31576
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017


---

# <a name="electronic-signature-overview"></a>Visão geral das assinaturas eletrônicas

[!include[banner](../includes/banner.md)]


Este artigo oferece uma visão geral de assinaturas eletrônicas e descreve como elas podem ser usadas no Microsoft Dynamics 365 for Finance and Operations.

<a name="what-is-an-electronic-signature"></a>O que é uma assinatura eletrônica?
--------------------------------

Uma assinatura eletrônica confirma a identidade de uma pessoa que está prestes a iniciar ou aprovar um processo de computação. Em algumas indústrias, uma assinatura eletrônica tem o mesmo valor legal que a assinatura manuscrita. As assinaturas eletrônicas são um requisito de regulamentações de conformidade para diversos setores regulamentados, como as indústrias farmacêutica, alimentícia, aeroespacial e de defesa. Também são necessárias para a conformidade com as regulamentações de 21 CFR Parte 11, emitidas pela FDA (agência de vigilância sanitária dos Estados Unidos). **Nota:** Uma assinatura eletrônica por si só não é o mesmo que uma assinatura digital. Uma assinatura eletrônica é simplesmente um substituto para uma assinatura manuscrita, ao passo que uma assinatura digital fornece medidas de segurança adicionais. Uma assinatura digital pode ajudar a identificar se outro usuário ou processo adulterou os dados. Uma assinatura digital também pode ser verificada e essa verificação não pode ser refutada pelo proprietário do certificado usado para assinar os dados. Conforme descrito abaixo, as assinaturas eletrônicas no Microsoft Dynamics 365 for Finance and Operations têm a funcionalidade interna de assinatura digital.

## <a name="electronic-signatures-in-dynamics-365-for-finance-and-operations"></a>Assinaturas eletrônicas no Dynamics 365 for Finance and Operations
No Finance and Operations, você pode usar assinaturas eletrônicas para processos comerciais críticos. Alguns processos têm recursos internos de assinatura eletrônica. Você também pode criar requisitos de assinatura personalizados para qualquer tabela e campo de banco de dados. As assinaturas eletrônicas têm uma funcionalidade interna de assinatura digital. Cada usuário que assina documentos deve obter um certificado criptográfico válido. Quando um documento é assinado, a chave privada associada ao certificado é validada. O Finance and Operations registra as informações de assinatura eletrônica em um log para fornecer uma trilha de auditoria. Para configurar as assinaturas eletrônicas, consulte [Configurar assinaturas eletrônicas (Guia de tarefas)](http://ax.help.dynamics.com/en/wiki/set-up-electronic-signatures/).

## <a name="users-who-require-access-to-electronic-signatures"></a>Usuários que precisam de acesso para assinaturas eletrônicas
Normalmente, três tipos de usuários requerem o acesso de segurança para assinaturas eletrônicas: administradores de assinatura eletrônica, signatários e auditores de assinatura eletrônica.

### <a name="electronic-signature-administrator"></a>Administrador de assinatura eletrônica

O administrador de assinatura eletrônica configura os requisitos de assinatura, os parâmetros gerais e os aprovadores, além de receber alertas quando assinaturas não puderem ser verificadas. Por padrão, um usuário que pertence à função de segurança **Gerente de tecnologia da informação** tem permissão para administrar assinaturas eletrônicas.

### <a name="signer"></a>Signatário

Um signatário fornece assinaturas eletrônicas para documentos e processos que exigem assinaturas. Por padrão, um usuário que pertence à função de segurança **Usuário do sistema** tem permissão para assinar documentos eletronicamente. **Observação:** O signatário pode exigir permissões adicionais antes de acessar os dados relacionados ao documento ou processo que está sendo assinado. Um usuário que altera dados e, em seguida, deve assinar essas alterações, deve ter permissão para alterar os dados. Um usuário que assina em nome de outro usuário talvez não exija acesso aos dados. Um exemplo desse tipo de usuário é um supervisor que assina alterações de um funcionário.

### <a name="electronic-signature-auditor"></a>Auditor de assinatura eletrônica

O auditor de assinatura eletrônica revisa o log do banco de dados e o log de revisão de assinatura disponível no log do banco de dados. Por padrão, um usuário que pertence à função de segurança **Gerente de tecnologia da informação** tem permissão para auditar assinaturas eletrônicas. Se você usar uma função diferente de **Gerente de tecnologia da informação**, certifique-se de que a função foi atribuída aos seguintes privilégios:

-   Exibir falhas de assinatura eletrônica
-   Exibir log do banco de dados

## <a name="signing-documents-electronically"></a>Assinando documentos eletronicamente
### <a name="get-a-certificate"></a>Obter um certificado

Antes de assinar documentos eletronicamente no Finance and Operations, você deve solicitar um certificado. **Nota:** O Finance and Operations usa recursos do Microsoft SQL Server para criar certificados e habilitar a assinatura eletrônica. Nenhuma infraestrutura de certificado ou de chave pública adicional (PKI) é necessária. Ao solicitar um certificado, uma chave pública e uma chave privada são criadas para você no banco de dados do Finance and Operations. A chave privada é criptografada usando uma senha que apenas você sabe. Ao assinar um documento eletronicamente, sua identidade é verificada quando você insere a senha. Para solicitar um certificado, na página **Opções**, na guia **Contas**, clique em **Adquirir certificado**. Você deve digitar e confirmar a senha usada para assinar. A senha será usada para proteger a chave privada e autorizar o uso do certificado. Essa senha não fica armazenada no banco de dados e não está disponível para mais ninguém, nem mesmo o administrador do Finance and Operations. Se você esquecer a senha associada ao certificado, ela deverá ser redefinida. A redefinição do certificado não afeta os documentos assinados com o certificado anterior. Para redefinir o certificado na página **Opções**, clique em **Redefinir certificado**.

### <a name="sign-a-document-electronically"></a>Assinar um documento eletronicamente

A página **Assinar documento** é exibida quando você faz uma alteração que requer um assinatura eletrônica.

1.  Na página **Atribuir documento**, clique na guia **Documento** para revisar as alterações do documento.
2.  Na guia **Assinatura**, selecione um código de motivo.
3.  Insira um comentário, se for necessário.
4.  Se a sua ID de usuário não for exibida no campo **Signatário**, selecione-a na lista.
5.  Insira sua localização, se essa informação for necessária.
6.  Clique em **OK**.

### <a name="sign-for-another-users-changes"></a>Assinar alterações de outro usuário

É possível que às vezes você deseje que um usuário assine as alterações de outro. Por exemplo, um supervisor pode ser responsável por assinar as alterações que um funcionário faz em uma lista de materiais (BOM). Use este procedimento para designar um usuário do Finance and Operations como um signatário de outro usuário. **Nota:** Quando um usuário assina a alteração de outro usuário, a assinatura deve ser fornecida na estação de trabalho do usuário que fez a alteração. O usuário não pode salvar a alteração até que a assinatura seja fornecida. Para designar aprovadores, siga estas etapas.

1.  Na página **Opções**, na guia **Contas**, clique em **Designar aprovação**.
2.  No campo **ID de usuário aprovador**, selecione a ID do usuário que deve assinar as alterações de outro usuário.
3.  No campo **Atribuir para ID de usuário**, selecione a ID do usuário cujas alterações devem ser assinadas.





