---
title: Entrada e navegação simplificada de funcionário
description: A entrada de dados para trabalhadores no Dynamics 365 for Talent foi aprimorada para permitir entrada rápida para todos os funcionários, do passado, ativos ou futuros. Um modelo de navegação simplificado/consolidado foi atualizado para localizar rapidamente as informações relacionadas e exibir e fazer as atualizações necessárias.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: be0253ffc4396f36050ef02c51a20d378e44473d
ms.sourcegitcommit: 4176c333ce3f88c5c68e95bd47e5791d32365dd2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1918185"
---
# <a name="streamlined-employee-entry-and-navigation"></a>Entrada e navegação simplificada de funcionário

[!include [banner](includes/banner.md)]

O Dynamics 365 for Talent permite a entrada eficiente do funcionário e dos dados de emprego. Você pode atualizar rapidamente as informações de histórico de trabalho para funcionários e prestadores de serviço do passado, ativos e futuros.

Você também pode habilitar uma experiência de navegação simplificada para localizar informações relacionadas rapidamente e fazer as alterações necessárias. Esta funcionalidade agora está disponível em ambientes de área restrita. Para ativar este recurso, navegue até **Administração do sistema > Links > Configuração > Parâmetros do sistema > Recursos de visualização**. Selecione **Formulário e a navegação aprimorados do Trabalhador**. Isso habilitará estas alterações para todos os usuários. Você pode desativar esta opção a qualquer momento.

## <a name="view-options"></a>Opções de exibição

Você pode usar **Opções de exibição** no formulário do trabalhador para selecionar qualquer combinação de funcionários ou prestadores de serviço de uma única lista. Essas opções permitem exibir trabalhadores entre entidades legais ou para a entidade legal na qual você está conectado no momento. Também é possível exibir trabalhadores ativos, pendentes e demitidos e você pode restringir os resultados com base no tipo de trabalhador (funcionário ou prestador de serviço). Se a segurança avançada estiver habilitada, você verá apenas os funcionários e prestadores de serviços nas entidades legais às quais tem acesso.

As colunas na exibição de lista são alteradas com base em suas seleções. Por exemplo, ao exibir funcionários demitidos, a data de demissão e os códigos de motivo são exibidos como colunas adicionais na lista. 

[![Opções de exibição](./media/Worker-view-option.png)](./media/worker-view-option.png)

## <a name="navigation-and-banner"></a>Navegação e banner

Uma faixa exibe as informações importantes de cada trabalhador. A faixa para trabalhadores ativos exibe os seguintes campos:

- **Cargo**
- **Departamento**
- **Tipo de posição**
- **Tipo de trabalhador**
- **Gerente**
- **Pessoa jurídica em geral**

A faixa para trabalhadores demitidos exibe os seguintes campos:

- **Data da saída**
- **Motivo**

A faixa para trabalhadores pendentes exibe os seguintes campos:

- **Cargo**
- **Departamento**
- **Tipo de posição**
- **Gerente**
- **Data inicial**
- **Pessoa jurídica em geral**

O painel de ações da página do trabalhador foi reorganizado para incluir menos opções. As informações agora são organizadas nas seguintes categorias: 

- Trabalho
- Pessoa
- Deixar
- Remuneração
- Benefícios
- Conformidade

Além disso, uma nova guia **Links** na página principal do trabalhador fornece aos usuários um local central para acessar todas as informações relacionadas a um trabalhador.

Devido a essas alterações, as informações podem aparecer em um local diferente do que você está acostumado. Por exemplo, as informações da folha de pagamento exibidas anteriormente no formulário do trabalhador agora aparecem no painel de ações em **Remuneração > Folha de Pagamento** e na guia **Informações Pessoais** agora tem um botão **Mais informações** para ocultar os campos que não são acessados com frequência.

[![Faixa](./media/Banner.png)](./media/Banner.png)

## <a name="work-history"></a>Histórico de trabalho

A guia **Histórico de trabalho** mostra o histórico de trabalho de todas as entidades legais e está disponível para funcionários e prestadores de serviço demitidos, ativos e pendentes. Agora você pode visualizar todo o histórico de trabalho de uma só vez para as entidades legais às quais você tem acesso. Além disso, você pode editar as informações de cada uma das entradas do histórico de trabalho sem alterar o contexto dos dados. Você pode atualizar todas as informações diretamente na página. 

[![Histórico de trabalho](./media/Worker-work-history.png)](./media/Worker-work-history.png)

## <a name="position-history"></a>Histórico de cargos

A guia **Cargos**, na página principal do trabalhador, fornece uma visão completa de todos os cargos ocupados na organização, incluindo atribuições passadas, presentes e futuras. Você ainda pode navegar diretamente para o histórico de cargos do trabalhador no painel de ações.

[![Cargos](./media/Worker-position-history.png)](./media/Worker-position-history.png)

