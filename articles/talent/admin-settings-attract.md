---
title: "Configurações de Administração no Attract"
description: "Este tópico explica como habilitar a funcionalidade de recursos para organizações e usuários no Attract."
author: 
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: be66d9f95551066bb8bc25445c652d4fa59066d4
ms.openlocfilehash: fb7b5e5b98ddb8e0e44fccbb0ddbb05199265414
ms.contentlocale: pt-br
ms.lasthandoff: 12/07/2018

---

# <a name="admin-settings-in-attract"></a>Configurações de Administração no Attract
[!include[banner](../includes/banner.md)]

O Centro de administração no Microsoft Dynamics 365 for Talent: Attract contém definições de configurações, opções de integração e opções de instalação para o aplicativo Attract.

## <a name="company-information"></a>Informações da empresa

Insira um nome de exibição da empresa e adicione um logotipo da empresa. O nome de exibição e o logotipo poderão então ser usados em lançamentos de trabalho e durante a experiência de integração.

## <a name="linkedin-integration"></a>Integração com o LinkedIn

Configure integração com o LinkedIn Recruiter System Connect (RSC). Depois que se conectar ao LinkedIn com suas credenciais do LinkedIn, você poderá sincronizar o perfil do LinkedIn de um candidato, as solicitações de emprego, os comentários da entrevista e as observações da equipe de contratação. Uma licença do recrutador completa do LinkedIn é necessária. Para obter mais informações sobre o LinkedIn Recruiter, consulte [Recruiter System Connect (RSC) – Perguntas frequentes](https://www.linkedin.com/help/recruiter/answer/90483).

## <a name="user-permissions"></a>Permissões de usuário

Atribua funções a usuários em sua organização. As funções a seguir estão disponíveis: **Administrador**, **Recrutador**, **Gerente de contratação**, e **Somente leitura**. Para obter mais informações sobre permissões de usuário, consulte [Gerenciamento de segurança e funções no Attract](./security-attract.md).

## <a name="feature-management"></a>Gerenciamento de recursos

Conforme os novos recursos forem adicionados, eles poderão ser liberados em uma visualização pública. Os recursos de visualização pública não atendem a todos os requisitos de serviço. Ao recebê-los, você concorda em compartilhar seus dados com sistemas externos. Você poderá notar que sua organização não necessita de todos os novos recursos que forem liberados. Você poderá ativar e desativar os recursos de visualização pública, dependendo das necessidades de sua organização.

## <a name="template-management"></a>Gerenciamento de modelos

Um modelo de processo contém todas as atividades que devem ser incluídas como parte do processo de contratação para um trabalho. Sua organização pode permitir que todos os membros da equipe ou que somente os administradores criem modelos de processo de contratação. Para permitir que os membros da equipe criem seus próprios modelos de processo de contratação, ative a funcionalidade Gerenciamento de modelos. Para obter mais informações sobre modelos de processo, consulte [Modelo de processo no Attract](./process-templates-attract.md).

## <a name="email-template-settings"></a>Configurações de modelo de email

As organizações podem criar modelos de email para vários cenários. Você pode selecionar a imagem do cabeçalho a ser incluída nos modelos de email. O cabeçalho selecionado aparecerá em todos os modelos de email. O rodapé do modelo, você poderá adicionar um link para a política de privacidade da organização e para os termos de uso das comunicações. Para obter mais informações, consulte [Modelos de email no Attract](./email-templates.md).

## <a name="offer-process"></a>Processo da oferta

Você pode configurar o processo de aprovação de ofertas de trabalho. Por exemplo, você pode especificar se uma oferta deve ser aprovada antes de ser enviada a um candidato. Você também pode exigir que os aprovadores deixem um comentário a decisão da oferta.

Dois fluxos de trabalho de aprovação estão disponíveis: **Paralelo** e **Sequencial**.

- **Paralelo** – as aprovações são enviadas para todos os aprovadores simultaneamente.
- **Sequencial** – as aprovações são enviadas para os aprovadores em uma ordem específica.

Você também pode configurar opções relacionadas à experiência do candidato. Por exemplo, uma opção permite especificar se os candidatos podem recusar uma oferta sem discussão adicional. Se você definir a opção **Permitir que os candidatos recusem uma oferta sem discussão adicional** como **Não**, o botão **Recusar oferta** ficará disponível para os candidatos. Se você definir esta opção como **Sim**, os candidatos poderão recusar a oferta selecionando um motivo e, em seguida selecionando **Recusar oferta**.

Também é possível definir e impor uma data de vencimento para as ofertas. Se você definir a opção **Requer uma data de vencimento para todas as ofertas** como **Sim**, a oferta expirará após o número de horas ou de dias especificado.

Para obter mais informações sobre o gerenciamento de ofertas, consulte [Configurar o gerenciamento de ofertas](./offer-setup.md).

