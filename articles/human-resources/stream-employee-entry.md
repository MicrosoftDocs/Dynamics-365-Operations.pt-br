---
title: Entrada e navegação simplificada de funcionário
description: A entrada de dados para trabalhadores no Dynamics 365 Human Resources fornece entrada rápida para todos os funcionários, do passado, ativos ou futuros.
author: twheeloc
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 477c44f62bd657770b50d65f1f8b8400dbe50022
ms.sourcegitcommit: 7181a022739d6107a75d84546c3379c23f722034
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8737754"
---
# <a name="streamlined-employee-navigation-and-entry"></a>Entrada e navegação simplificada de funcionários

O Dynamics 365 Human Resources permite a entrada eficiente do funcionário e dos dados de emprego. Você pode atualizar rapidamente as informações de histórico de trabalho para funcionários e prestadores de serviço do passado, ativos e futuros.

## <a name="view-options"></a>Opções de exibição

Você pode usar **Exibir opções** no formulário **Trabalhador** para selecionar qualquer combinação de funcionários ou prestadores de serviço de uma única lista. Essas opções permitem exibir trabalhadores entre entidades legais ou para a entidade legal na qual você está conectado no momento. Também é possível exibir trabalhadores ativos, pendentes e demitidos e você pode restringir os resultados com base no tipo de trabalhador (funcionário ou prestador de serviço). Se a segurança avançada estiver habilitada, você verá apenas os funcionários e prestadores de serviços nas entidades legais às quais tem acesso.

As colunas na exibição de lista são alteradas com base em suas seleções. Por exemplo, ao exibir funcionários demitidos, a data de demissão e os códigos de motivo são exibidos como colunas adicionais na lista. 

## <a name="navigation-and-banner"></a>Navegação e banner

Uma faixa exibe as informações importantes de cada trabalhador. A faixa para trabalhadores ativos exibe as seguintes colunas:

- **Cargo**
- **Departamento**
- **Tipo de posição**
- **Tipo de trabalhador**
- **Gerente**
- **Pessoa jurídica em geral**

A faixa para trabalhadores demitidos exibe as seguintes colunas:

- **Data da saída**
- **Motivo**

A faixa para trabalhadores pendentes exibe as seguintes colunas:

- **Cargo**
- **Departamento**
- **Tipo de posição**
- **Gerente**
- **Data inicial**
- **Pessoa jurídica em geral**

O painel de ações da página **Trabalhador** foi reorganizado para incluir menos opções. As informações são organizadas nas seguintes categorias: 

- Trabalho
- Pessoa
- Sair
- Remuneração
- Benefícios
- Conformidade

Além disso, uma nova guia **Links** na página **Trabalhador** fornece aos usuários um local central para acessar todas as informações relacionadas a um trabalhador.


## <a name="work-history"></a>Histórico de trabalho

A guia **Histórico de trabalho** mostra o histórico de trabalho de todas as entidades legais e está disponível para funcionários e prestadores de serviço demitidos, ativos e pendentes. Você pode exibir todo o histórico de trabalho de uma só vez para as entidades legais às quais você tem acesso. Além disso, você pode editar as informações de cada uma das entradas do histórico de trabalho sem alterar o contexto dos dados. Você pode atualizar todas as informações diretamente na página. 


## <a name="position-history"></a>Histórico de cargos

A guia **Cargos**, na página principal do trabalhador, fornece uma visão completa de todos os cargos ocupados na organização, incluindo atribuições passadas, presentes e futuras. Você pode navegar diretamente para o histórico de cargos do trabalhador no painel de ações.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
