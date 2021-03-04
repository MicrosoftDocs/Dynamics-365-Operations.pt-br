---
title: Novidades ou alterações no Dynamics 365 Talent (21 de janeiro de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e9dee64e94c904cfe07c6a7766f6a60b1d60a2db
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528110"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-21-2020"></a>Novidades ou alterações no Dynamics 365 Talent (21 de janeiro de 2020)

[!include [banner](includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract. Adicionamos funcionalidades ao Attract para dar suporte ao nosso anúncio recente, [Construindo uma força de trabalho mais bem-sucedida com o Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources/).

### <a name="download-environment-data"></a>Fazer download dos dados do ambiente

Os administradores podem fazer download dos seus dados do ambiente. Os dados são exportados no formato JSON padrão com todos os trabalhos, candidatos e a configuração exportados em um arquivo zip. Para obter mais informações, consulte [Exportar dados do Attract e do Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

### <a name="restricting-access-to-environments-for-non-admin-users"></a>Restrição de acesso a ambientes para usuários não administradores

Agora, os administradores podem restringir o acesso ao ambiente para usuários não administradores. Essa ação não pode ser desfeita. Para obter mais informações, consulte [Restrição de acesso ao Attract](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data#restrict-access-to-attract).

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

### <a name="exporting-onboarding-guides"></a>Exportação de guias de integração

Agora, os usuários podem exportar todas as guias e modelos de integração no formato de documento do Word. Para obter mais informações, consulte [Exportar dados do Attract e do Onboard](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2726. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="most-recent-annual-compensation-field-in-verify-employment-form-isnt-consistent-392092"></a>O campo de remuneração anual mais recente no Formulário de verificação de emprego não está consistente (392092)

Esta versão inclui uma alteração que exibirá de forma consistente a moeda mais recente com base no seletor da empresa no formulário **Verificação de emprego**.

### <a name="known-as-field-added-to-the-feedback-recipient-lookup-407789"></a>Campo Conhecido como adicionado à pesquisa de Comentários do destinatário (407789)

Ao fornecer comentários sobre o desempenho, a pesquisa para trabalhadores não forneceu informações suficientes para determinar se os comentários estão indo para a pessoa correta. Adicionamos uma coluna **Conhecido como** para ajudar a identificar o nome exclusivo do funcionário.
 
### <a name="hcmworkerpayrollinfo-record-is-created-without-an-association-to-a-worker-394526"></a>O registro HcmWorkerPayrollInfo é criado sem uma associação a um trabalhador (394526)

Essa versão inclui uma alteração para não gravar registros de HCMWorkerPayrollInfo sem referência a um funcionário.

### <a name="able-to-edit-department-when-navigating-from-position-hierarchy-341001"></a>Capaz de editar o departamento enquanto navega na hierarquia de posição (341001)

Quando a segurança é configurada para negar acesso aos departamentos de edição, a edição é desabilitada ao navegar para o formulário **Departamentos** em todos os cenários.

## <a name="coming-soon"></a>Em breve

Uma nova solução de Common Data Service estará disponível em breve com as seguintes alterações:

| Descrição | Troco |
| --- | --- |
| Alterações de entidade do **Trabalho/Posição** | <ul><li>**Região de remuneração** adicionado</li><li>**Dimensões financeiras** adicionado</li></ul> |
| Alterações de entidade do **Trabalhador** | <ul><li>**Sequência do nome** adicionado</li><li>**Trabalha de casa** adicionado</li><li>**Idioma** adicionado</li><li>**Aniversário de tempo de serviço** adicionado</li><li>**Data de aniversário** adicionado</li><li>**Data original de contratação** adicionado</li></ul> |
| Alterações de entidade do **Emprego** | <ul><li>**Dimensões financeiras** adicionado</li><li>**Motivo da demissão** adicionado</li><li>**Data da demissão** renomeada de **Data de transição**</li><li>**Data de experiência** adicionado</li></ul> |
| Alterações de entidade do **Endereço do trabalhador** | <ul><li>**Endereço** adicionado</li><li>**Linha de endereço 1**, **Linha de endereço 2** e **Linha de endereço 3** marcadas para depreciação</li></ul> |
| Novas entidades de configuração de remuneração variável | <ul><li>**Tipo de plano de remuneração variável**</li><li>**Plano de remuneração variável**</li><li>**Regras de benefício proporcional diferido**</li><li>**Nível do plano de remuneração variável**</li></ul> |
| Nova entidade **Emprego do calendário do trabalhador** | <ul><li>**Entidade do calendário de trabalho** adicionada</li></ul> |


[!INCLUDE[footer-include](../includes/footer-banner.md)]