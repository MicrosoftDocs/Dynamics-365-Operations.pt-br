---
title: Acumular folga com base nas horas trabalhadas
description: Este tópico descreve como os planos de licença podem ser configurados para acumular folga com base nas horas trabalhadas.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
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
ms.author: anbichse
ms.search.validFrom: 2018-09-17
ms.dyn365.ops.version: ''
ms.openlocfilehash: 938d2eea7b9e85b19e9c1e3e0930f625224b880d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898610"
---
# <a name="accrue-time-off-based-on-hours-worked"></a>Acumular folga com base nas horas trabalhadas

## <a name="overview"></a>Visão Geral

As organizações com funcionários com taxa horária podem conceder folga com base nas horas trabalhadas, em vez de no tempo de serviço na organização. Os dados de horas trabalhadas geralmente são armazenados em um sistema de horário e presença. No Talent: Core HR, essas horas normais e as horas extras trabalhadas podem ser importadas e usadas como base para uma premiação do funcionário.

## <a name="leave-plans"></a>Planos de licença

No plano de licença, o tipo de acumulação pode ser meses de serviço ou horas trabalhadas. Quando for selecionada a opção horas trabalhadas, haverá dois tipos de horas a serem usados para a acumulação: normal e hora extra.

Para configurar um plano de licença para usar as horas trabalhadas, siga estas etapas:

1. Na página **Planos de licença e ausência** , clique em **Criar novo plano**.
2. Insira um nome para o plano de licença.
3. Selecione a frequência da competência do plano.
5. Selecione a data inicial do plano.
6. Escolha a base do período de acumulação e selecione a data específica do funcionário, se aplicável.
7. Para a agenda de acumulação, selecione **Horas trabalhadas** para o tipo de acumulação.
8. Selecione o tipo de horas a ser usado para a acumulação.
9. Insira o número de horas trabalhadas e o valor de acumulação, saldo mínimo, e valor máximo de premiação e postergação associados.

O processamento da acumulação dos planos de horas trabalhadas usa a frequência de acumulação, junto com a base do período de acumulação para determinar as horas a serem acumuladas.

## <a name="annual-accrual-frequency"></a>Frequência de acumulação anual

| Data de premiação de acumulação    | Camada de horas trabalhadas    | Valor da competência        | Datas de horas trabalhadas   | Valores reais de horas trabalhadas| Prêmio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2000                | 0                 |


## <a name="monthly-accrual-frequency"></a>A frequência de acumulação mensal

| Data de premiação da acumulação    | Camada de horas trabalhadas    | Valor da competência        | Datas de horas trabalhadas   | Valores reais de horas trabalhadas| Prêmio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 8/1/2018-31/8/2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 8/1/2018-31/8/2018   | 184                 | 3                   |

## <a name="semi-monthly-accrual-frequency"></a>A frequência de acumulação quinzenal

| Data de premiação da acumulação    | Camada de horas trabalhadas    | Valor da competência        | Datas de horas trabalhadas   | Valores reais de horas trabalhadas| Prêmio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 8/16/2018-31/8/2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 8/16/2018-31/8/2018  | 75                  | 0                   |

## <a name="weekly-accrual-frequency"></a>A frequência de acumulação semanal

| Data de premiação da acumulação    | Camada de horas trabalhadas    | Valor da competência        | Datas de horas trabalhadas   | Valores reais de horas trabalhadas| Prêmio               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 8/27/2018-31/8/2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 8/27/2018-31/8/2018  | 35                  | 0                   |

## <a name="employee-assigned-leave-plans"></a>Planos de licença atribuídos ao funcionário

Nos planos de licença atribuídos ao funcionário, a base da camada e o tipo de horas são exibidos para os planos nos quais as horas trabalhadas são definidas como tipo de acumulação. Para planos ativos, horas trabalhadas reais para os períodos de acumulação a partir da data atual também são exibidas para referência. 

## <a name="loading-data"></a>Carregando dados

As horas reais podem ser importadas usando a entidade de Horas de licença e de ausência trabalhadas no gerenciamento de dados. Se estiver usando calendários de horário de trabalho, a importação validará as horas normais trabalhadas que não excedam as horas programadas em um dia definido pelo calendário. A importação também valida as horas trabalhadas por determinado dia que não excedam 24 horas. 

As informações a seguir são necessárias para importar as horas reais a serem usadas no processo de acumulação de licença:

+ Número da equipe 
+ Data de trabalho
+ Tipo
+ Horas

Uma única data só pode ter um de cada tipo associado a ela.

| NÚMERO DA EQUIPE       | DATA DE TRABALHO           | TIPO                  | HORAS                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Normal               | 8                    |       
| 000337                | 8/7/2018             | Normal               | 8                    |
| 000337                | 8/7/2018             | Hora extra              | 3                    |
| 000337                | 8/8/2018             | Normal               | 8                    |
| 000337                | 8/7/2018             | Normal               | 8                    |
| 000337                | 8/9/2018             | Normal               | 8                    |
