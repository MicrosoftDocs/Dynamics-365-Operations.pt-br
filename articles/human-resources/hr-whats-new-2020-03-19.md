---
title: Novidades ou alterações no Dynamics 365 Human Resources (19 de março de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d6988bb95cf2ffe8146434f4b194d97491952915
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157359"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-19-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (19 de março de 2020)

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3014. Os números entre parênteses em alguns cabeçalhos referem-se aos números de suporte do Lifecycle Services (LCS) para referência.

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Os limites do ambiente do Human Resources agora são baseados em licenciamento atualizado (394595)

O limite em relação ao número de ambientes por projeto no Lifecycle Services (LCS) mudou. O limite anterior era de dois ambientes. O limite em relação ao número de ambientes de produção e área restrita que você pode criar para Human Resources no LCS agora se baseia no licenciamento atualizado. Agora você pode criar quantos ambientes forem necessários por projeto do LCS, dependendo do número de licenças adquiridas. O novo licenciamento, atualizado em 1º de fevereiro de 2020, permite que os clientes adquiram ambientes adicionais. Para obter mais informações sobre requisitos de licenciamento para ambientes adicionais, consulte [Guia de licenciamento do Dynamics 365](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="provide-cross-company-viewing-of-compensation-data-for-employees-and-managers-403904"></a>Fornecer visualização entre empresas de dados de remuneração para funcionários e gerentes (403904)

Ative esse recurso na área de trabalho **Gerenciamento de recursos**. Para obter mais informações, consulte [Habilitar ou desabilitar recursos de visualização](hr-admin-manage-features.md#enable-or-disable-preview-features).

Quando você habilita esse recurso, os gerentes podem ver a remuneração de subordinados diretos e estendidos sem precisar se conectar à empresa do trabalho. O histórico de remuneração completo está disponível em qualquer empresa conectada que o gerente possa acessar. Para obter mais informações, consulte [Visão geral de autoatendimento de Funcionário e Gerente](hr-employee-manager-self-service-overview.md).

## <a name="enable-global-address-book-merge-functionality-427189"></a>Habilitar a funcionalidade de mesclagem do catálogo de endereços global (427189)

Agora você pode mesclar entradas duplicadas do catálogo de endereços selecionando os registros duplicados e escolhendo **Mesclar** na página **Catálogo de endereços global**.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-the-multiple-leave-type-feature-on-419635"></a>Não foi possível ajustar o saldo de licenças de um plano sem competências que foi criado com o recurso Vários tipos de licença em (419635)

Agora você pode ajustar os saldos dos planos de licenças criados com o recurso de visualização **Vários tipos de licença** habilitado no Gerenciamento de recursos.

## <a name="primary-position-field-in-the-workerpositionassignmententity-when-an-employee-is-terminated-420774"></a>Campo de cargo principal em WorkerPositionAssignmentEntity quando um funcionário é demitido (420774)

Para funcionários com um trabalho encerrado, o cargo principal que estava ativo no momento da rescisão é exibido na entidade. Em integrações, um registro duplicado não será mais criado para a atribuição de cargo do trabalhador do funcionário. 

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>A solução do Common Data Service agora está disponível com as seguintes alterações:

| descrição | Troco |
| --- | --- |
| Alterações de entidade do **Trabalho/Posição** | <ul><li>**Região de remuneração** adicionado</li>|
| Entidade **Dimensão da posição do trabalho** adicionada | <ul><li>**Dimensões financeiras** adicionado</li>
| Alterações de entidade do **Trabalhador** | <ul><li>**Sequência do nome** adicionado</li><li>**Trabalha de casa** adicionado</li><li>**Idioma** adicionado</li><li>**Aniversário de tempo de serviço** adicionado</li><li>**Data de aniversário** adicionado</li><li>**Data original de contratação** adicionado</li></ul> |
| Alterações de entidade do **Emprego** | <ul><li>**Dimensões financeiras** adicionado</li><li>**Motivo da demissão** adicionado</li><li>**Data da demissão** renomeada de **Data de transição**</li><li>**Data de experiência** adicionado</li></ul> |
| Alterações de entidade do **Endereço do trabalhador** | <ul><li>**Endereço** adicionado</li><li>**Linha de endereço 1**, **Linha de endereço 2** e **Linha de endereço 3** marcadas para depreciação</li></ul> |
| Novas entidades de configuração de remuneração variável | <ul><li>**Tipo de plano de remuneração variável**</li><li>**Plano de remuneração variável**</li><li>**Regras de benefício proporcional diferido**</li><li>**Nível do plano de remuneração variável**</li></ul> |
| Nova entidade **Emprego do calendário do trabalhador** | <ul><li>**Entidade do calendário de trabalho** adicionada</li></ul> |
| Nova entidade **Detalhe da posição de folha de pagamento** | <ul><li>**Detalhe da posição de folha de pagamento** adicionado</li></ul> |
| Nova entidade **Bloco** | <ul><li>**Bloco** adicionado</li></ul>A nova entidade **Título** é incluída no Common Data Service, mas não é referenciada nas entidades **Posição de trabalho** ou **Trabalho** no momento. |

> [!NOTE]
> As dimensões financeiras para as posições e o trabalho fornecem integração unidirecional para atualizações de recursos humanos para Common Data Service. As atualizações de dimensões financeiras não são sincronizadas atualmente de Common Data Service a Recursos Humanos.

Nas próximas semanas, essas alterações de entidade estarão disponíveis em todos os ambientes. Para instalar manualmente a solução Common Data Service mais recente para recursos humanos:

1.  Vá para [Centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2.  Selecione **Ambientes**.

3.  Localize o ambiente que você deseja atualizar. O ambiente deve corresponder ao **Nome do ambiente** na seção **informações do Common Data Service** no formulário **Sobre** em Recursos Humanos.

4.  Selecione o ambiente para exibir os detalhes do ambiente.

5.  Na barra de ação na parte superior, selecione **Gerenciar soluções**. Uma nova janela do navegador irá abrir e navegar até o **Centro de Administração do Dynamics 365** no contexto do seu ambiente.

6.  Na lista **Solução**, selecione **Ancoragem de Dynamics 365 Human Resources**.

7.  Selecione **Atualizar** para aplicar a solução mais recente.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>A visualização do SharePoint não funcionará em alguns ambientes

Se a visualização de documentos armazenados no SharePoint não funcionar, tente o seguinte procedimento:

1. Verifique se a conta de usuário do administrador possui um email associado ao registro do usuário. Você pode exibir essas informações na página **Usuário**. Se o email não estiver configurado, você precisará adicionar o email e o provedor com o suplemento do OData Excel. Por padrão, o endereço de email não está presente no design do Excel. Será preciso editar o design do Excel, adicionar todos os campos, aplicar e atualizar. Depois de concluir essas etapas, você pode atualizar a conta de administrador.

2. Depois que a conta de administrador tiver uma conta de email associada, entre no Human Resources com credenciais de administrador.

3. Acesse um anexo no SharePoint para iniciar a visualização do documento.

4. Entre com outra conta de usuário que tenha acesso a anexos e verifique se a visualização funciona conforme o esperado.

## <a name="coming-soon"></a>Em breve

### <a name="platform-update-33"></a>Update 33 para plataforma

- Aplicativos de página completa (Visualização) - Esse recurso de visualização, que requer que você habilite o recurso de Exibições salvas, permite que Power Apps e aplicativos de terceiros sejam adicionados como experiências de página completa por meio do painel.

- Exibições salvas (Visualização) - Este recurso de visualização habilita exibições salvas, que fornece um aperfeiçoamento significativo do subsistema de personalização. Esse recurso permite que os usuários tenham vários conjuntos nomeados de personalizações por página. Você também pode publicar exibições para direitos de acesso.

- Otimizado "é uma das" experiências de filtragem - este recurso permite que uma experiência de filtragem otimizada como "é uma das" que facilita inserir vários valores de filtro, tem um mecanismo mais simples para remover valores individuais ou de todos os filtros, e tem uma visualização mais compacta e intuitiva de valores de filtro.

- Campos recomendados - Geralmente, os usuários precisam adicionar campos a uma grade ou a uma página. Isso pode ser difícil com tantos campos disponíveis. Em vez de ter de pesquisar uma lista grande, este recurso permite que o sistema alcance um conjunto de campos recomendados com base no que os outros usuários adicionam com mais frequência em cenários semelhantes.

- Ações adesivas padrão em grades-este recurso garante que a ação padrão em uma grade esteja vinculada a uma coluna específica em uma grade, independentemente da coluna ser movida ou ocultada.

## <a name="new-production-release-cadence"></a>Nova cadência de liberação da produção

A partir de abril, a cadência de liberação do Human Resources passará de uma atualização semanal para uma atualização quinzenal. Isso garantirá o alinhamento com as práticas de implantação segura e manterá altos padrões de estabilidade e confiabilidade no serviço. Estamos implementando testes e monitores adicionais para verificar a implantação bem-sucedida em cada estágio do processo. Para obter mais informações sobre a cadência de liberação, consulte [Atualizar processo](hr-admin-setup-update-process.md).

## <a name="in-preview"></a>Em visualização

Os seguintes recursos de visualização foram disponibilizados em 3 de fevereiro de 2020:

- **Recursos de exibição de licenças e ausências** - para obter mais informações, consulte [Recursos de exibição de licenças e ausências](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Recurso de visualização de gerenciamento de benefícios** - para obter mais informações, incluindo problemas conhecidos, consulte [Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md).

