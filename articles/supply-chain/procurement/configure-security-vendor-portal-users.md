---
title: "Segurança de usuário do portal do fornecedor"
description: "Este artigo explica como configurar a segurança para fornecedores externos que usam o Portal do fornecedor. Estas informações só se aplicam a versões de fevereiro de 2016 &amp; maio de 2016 do Dynamics AX."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 560e0760c33cab4186095ac2ae7e105d75cc16d0
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="vendor-portal-user-security"></a>Segurança de usuário do portal do fornecedor

[!include[banner](../includes/banner.md)]


Este artigo explica como configurar a segurança para fornecedores externos que usam o Portal do fornecedor. Estas informações só se aplicam a versões de fevereiro de 2016 &amp; maio de 2016 do Dynamics AX.

A funcionalidade de portal do fornecedor foi substituída por uma funcionalidade estendida de colaboração do fornecedor na versão 1611 do Dynamics 365 for Operations. Para obter mais informações sobre como configurar a segurança para a colaboração de fornecedor, consulte [Instalação e manutenção da colaboração de fornecedor](set-up-maintain-vendor-collaboration.md). O portal do fornecedor expõe um conjunto limitado de informações sobre ordens de compra (POs) para fornecedores externos. É importante que você configure corretamente as permissões do usuário para o portal do fornecedor no Microsoft Dynamics AX, de modo que os fornecedores não tenham acesso não intencional a informações adicionais sobre a instalação do Dynamics AX. **Importante:** Diferente dos outros usuários, os fornecedores externos não devem ter a função **SystemUser**. A função **SystemUser** concede acesso a um conjunto de privilégios que não são adequados para usuários externos.

## <a name="setting-up-a-vendor-portal-user"></a>Configurando um usuário do portal do fornecedor
Antes de criar uma conta de usuário para alguém que usará o portal do fornecedor, configure o fornecedor para permitir a colaboração do portal do fornecedor. Use o campo **Colaboração da ordem de compra** na guia **Geral** da página **Fornecedores**. Os fornecedores externos que usam o portal do fornecedor devem ter a seguinte configuração:

-   Uma conta de usuário do AAD (Active Directory do Microsoft Azure) deve ser registrada para o fornecedor na página **Usuários** do Dynamics AX.
-   O fornecedor deve ter a função de segurança **Fornecedor (externo)**, e não a função **SystemUser**. **Observação:** a função **SystemUser** é concedida automaticamente quando você cria uma nova conta de usuário no Dynamics AX. Portanto, remova essa função e confirme a mensagem de aviso recebida.
-   O usuário fornecedor não deve receber permissão para adicionar campos extras das tabelas de OC à exibição da OC. Na guia **Personalização**, na guia **Usuários**, defina a opção **Personalização explícita permitida** do usuário para **Não**.
-   A conta de usuário deve ser associada à pessoa de contato registrada. Na página **Usuários**, selecione uma pessoa de contato no campo **Nome**. A pessoa selecionada deve ter a função **Contato** do fornecedor relevante.

Se a mesma pessoa precisar de acesso ao portal do fornecedor em várias contas de fornecedor (para entidades legais diferentes, talvez), cada uma das contas de usuário dessa pessoa deverá ser associada com à mesma pessoa de contato registrada. A função **Fornecedor (externo)** inclui todos os recursos básicos necessários para usar a funcionalidade disponibilizada no portal do fornecedor. Essa configuração garante que a interface do usuário exibida para o usuário externo terá como foco apenas o cenário desejado.

<a name="see-also"></a>Consulte também
--------

[Colaboração do fornecedor](collaborate-vendors-vendor-portal.md)



