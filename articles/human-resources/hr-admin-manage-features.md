---
title: Gerenciar recursos em Recursos Humanos
description: Este tópico descreve o recurso de gerenciamento de recursos e como você pode usá-lo.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61e40f7177a1c8cf3d60a9a991ecbb0ed4d93aa1
ms.sourcegitcommit: 72a82e9aeabbdecf57e1aee72975c63eba75143a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7414624"
---
# <a name="manage-features-in-human-resources"></a>Gerenciar recursos em Recursos Humanos

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Como parte de liberação contínua de novas funcionalidades do Microsoft Dynamics 365 Human Resources, queremos que nossos clientes aproveitem novos recursos o mais rápido possível. Fornecemos recursos de visualização, que estão quase prontos para disponibilidade geral e passam por um teste extenso. Estamos procurando apenas um círculo final de comentários de cliente e validação antes de liberá-los para disponibilidade geral.

Para obter mais informações sobre novos recursos no Human Resources, consulte [Novidades em Human Resources](hr-admin-whats-new.md) e [Dynamics 365 e Plano de versão do Power Platform](/dynamics365/release-plans/?panel=products1#pivot=products).

O espaço de trabalho **Gerenciamento de recursos** fornece uma lista de recursos entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles. Para obter mais informações sobre o Gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Todos os novos recursos permanecerão em versão prévia por pelo menos 30 dias e, em geral, por 30 a 60 dias. Os recursos principais estão disponíveis geralmente em outubro e abril de cada ano a partir do período de versão prévia. Assim que vir novos recursos no espaço de trabalho **Gerenciamento de recursos**, você poderá ativá-los. Alguns recursos podem ser ativados por padrão.

Assim que um recurso estiver disponível de forma geral, ele poderá ser ativado ou desativado em ambientes de produção. O espaço de trabalho **Gerenciamento de recursos** indica quando a versão prévia do recurso se tornará obrigatória. Geralmente, essa data fica entre 1º de outubro ou 1º de abril, para se alinhar com os planos de lançamento semestrais. Você não pode desativar recursos obrigatórios. Até que ele se torne obrigatório, você poderá ativar e desativar um recurso em todos os ambientes.

## <a name="enable-or-disable-preview-features"></a>Habilitar ou desabilitar recursos de visualização

Para acessar os recursos de visualização, primeiro é preciso ativá-los no ambiente. A habilitação ou desabilitação de recursos de visualização é específica do ambiente.

> [!IMPORTANT]
> Os recursos da versão prévia estão disponíveis somente em ambientes de **Área restrita**. Quando você ativa um recurso de visualização, você os habilita para todos os usuários da organização que estão no ambiente. Ao desativar o recurso de visualização, você o desabilita e o torna inacessível a seus usuários. Os recursos de visualização limitaram o suporte em Human Resources. Eles podem usar menos medidas de privacidade e segurança, e elas não estão incluídas no contrato de nível de serviço (SLA) de Human Resources. Você não deve usar recursos de visualização para processar dados pessoais (isso é, quaisquer informações que podem identificar você), ou para processar outros dados que estão sujeitos a requisitos de conformidade regulatório.

1. No Human Resources, selecione **Administração do sistema**.

2. Selecione o bloco **Gerenciamento de recursos**.

3. Para habilitar um recurso de visualização, selecione-o na lista e, em seguida, selecione **Habilitar**. Para desabilitar um recurso de visualização, selecione-o na lista e, em seguida, selecione **Desabilitar**.

## <a name="enable-or-disable-benefits-management"></a>Habilitar ou desabilitar o Gerenciamento de benefícios

Para habilitar o gerenciamento de benefícios, use o mesmo procedimento em [Habilitar ou desabilitar recursos de visualização](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> Não é possível desabilitar o gerenciamento de benefícios em um ambiente de **Produção** após ativá-lo. No entanto, você pode desabilitar o gerenciamento de benefícios em ambientes de **Área restrita**.

Para obter mais informações sobre a configuração e o uso do gerenciamento de benefícios, consulte [Visão geral do Gerenciamento de benefícios](hr-benefits-management-overview.md).

O gerenciamento de benefícios substitui a funcionalidade do espaço de trabalho de **Benefícios**. Ao habilitar o recurso de visualização de gerenciamento de benefícios, não será mais possível acessar os seguintes formulários no espaço de trabalho **Benefícios**:

- **Benefícios**
- **Elementos do benefício**
- **Taxas de cálculo de contribuição**
- **Resultados da inscrição no benefício**
- **Resultados da expiração e da extensão de benefícios**
- **Tipos de regras de política de qualificação para o benefício**
- **Políticas de qualificação para benefícios**
- **Eventos de qualificação**

Você pode exibir as informações destas páginas no modo somente leitura. Se desejar editar as informações, você deve primeiro desabilitar o gerenciamento de benefícios (aplicável apenas a ambientes de **Área restrita**).

## <a name="enable-or-disable-leave-and-absence"></a>Habilitar ou desabilitar a licença e a ausência

Para habilitar Licença e ausência, use o mesmo procedimento em [Habilitar ou desabilitar recursos de visualização](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> Você não pode desabilitar o recurso **Vários tipos de licença** na Licença e ausência após ativá-lo. Isso aplica-se a ambientes de **Área restrita** e **Produção**.

Para obter mais informações sobre recursos de visualização em Licenças e ausência, consulte [Recursos de exibição de licenças e ausências](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

## <a name="send-us-feedback"></a>Envie seus comentários

Queremos saber sua experiência com esses recursos de visualização. É recomendável postar regularmente seus comentários nos sites a seguir conforme você os usa ou quaisquer outros recursos:

- [Comunidade](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) Este site é um ótimo recurso onde os usuários podem discutir casos de uso, fazer perguntas e obter ajuda da comunidade.
- Conte para nós os recursos que você deseja ver no produto ou as alterações que você acha que devemos fazer nos recursos existentes. Sugerir ideias de produtos em [Ideias de Human Resources](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources).
    
Não inclua dados pessoais (qualquer informação que pode te identificar) em seus comentários ou envios de análise do produto. Informações coletadas podem ser analisadas mais profundamente, e elas não serão usadas para atender a solicitações em leis aplicáveis de privacidade. Dados pessoais que são coletados separadamente nestes programas estão sujeitos à [Política de Privacidade online da Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Consulte também

- [Novidades em Human Resources](hr-admin-whats-new.md)
- [Dynamics 365 e Plano de versão do Power Platform](/dynamics365/release-plans/?panel=products1#pivot=products)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
