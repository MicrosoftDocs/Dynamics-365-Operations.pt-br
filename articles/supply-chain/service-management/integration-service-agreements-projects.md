---
title: Integração dos contratos de serviço e projetos
description: Quando você trabalha com contratos de serviço e linhas de contrato de serviço, usa os dados configurados nas áreas em Gerenciamento e contabilidade do projeto.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9855915bd4d1f8ebb0c73bf53e7032af4972c45
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831546"
---
# <a name="integration-for-service-agreements-and-projects"></a>Integração dos contratos de serviço e projetos 

[!include [banner](../includes/banner.md)]


Quando você trabalha com contratos de serviço e linhas de contrato de serviço, usa os dados configurados nas seguintes áreas em **Gerenciamento e contabilidade do projeto**.

## <a name="project-prices"></a>Preços do projeto

O preço de custo e de venda de uma transação de contrato de serviço derivam da configuração de preço de custo que se aplica ao projeto associado ao contrato de serviço. Os preços de custo e de venda podem ser configurador por projeto, funcionário e categoria. 

## <a name="project-validation"></a>Validação de projeto

Os projetos, os funcionários e as categorias disponíveis para seleção em uma linha de contrato de serviço podem ser limitados pela configuração de validação em **Gerenciamento e contabilidade do projeto**. Usando a configuração de validação, você pode combinar funcionários, projetos e categorias para acesso controlado. 

## <a name="project-line-properties"></a>Propriedades da linha de projeto

Uma propriedade de linha é inserida automaticamente para uma linha de contrato de serviço.

As propriedades de linha são criadas no formulário **Propriedades de linha** em **Gerenciamento e contabilidade de projeto**. A propriedade da linha inserida em um contrato de serviço é anexada ao projeto selecionado para o contrato e, subsequentemente, herdada subsequentemente pela linha do contrato de serviço. 

## <a name="default-offset-accounts"></a>Contrapartidas padrão

Se você inserir uma transação de despesa, uma contrapartida de despesa padrão será selecionada automaticamente para a transação. A conta de despesa padrão é configurada para o projeto associado ao contrato de serviço atual.

## <a name="project-categories"></a>Categorias de projeto

As categorias disponíveis para as linhas do contrato de serviço são configuradas no formulário **Categorias de projeto** na seção **Gerenciamento e contabilidade do projeto**. 

> [!NOTE]
> <P>As categorias que têm a caixa de seleção <STRONG>Ativo em diários</STRONG> marcada na guia <STRONG>Projeto</STRONG> do formulário <STRONG>Categorias de projeto</STRONG> estão disponíveis para seleção. Porém, se a caixa de seleção <STRONG>Categorias inativas</STRONG> estiver selecionada na guia <STRONG>Diários</STRONG> no formulário <STRONG>Parâmetros de gerenciamento do projeto e a contabilidade</STRONG>, todas as categorias estarão disponíveis para seleção.</P>

## <a name="project-parameters"></a>Parâmetros do projeto

Se o campo **Trabalhadores demitidos** na guia **Diários** no formulário **Parâmetros de gerenciamento e contabilidade de projetos** for selecionada, você pode selecionar funcionários inativos e ativos nos formulários **Contratos de serviço** e **Ordens de serviço**.

Você também poderá habilitar os campos **Hora de início** e **Hora de término** na guia **Projeto** do formulário **Ordens de serviço** para especificar horários de início e término em linhas de ordem de serviço.

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>Habilitar o recurso de horário de início e término para ordens de serviço

1.  Clique em **Gerenciamento e contabilidade de projetos** \> **Configurar** \> **Parâmetros de gerenciamento e contabilidade de projetos**.

2.  Clique na guia **Diários**, e depois marque a caixa de seleção **Mostrar horas de início/término**.

3.  Clique em **Gerenciamento e contabilidade de projetos** \> **Configuração** \> **Diários** \> **Nomes de diário**.

4.  Selecione o nome do diário anexado à ordem de serviço.

5.  Clique na guia **Geral**, e depois marque a caixa de seleção **Mostrar horas de início/término**.


> [!NOTE]
> <P>Selecione o nome do diário para a ordem de serviço no campo <STRONG>Hora</STRONG> na guia <STRONG>Diários</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG>.</P>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]