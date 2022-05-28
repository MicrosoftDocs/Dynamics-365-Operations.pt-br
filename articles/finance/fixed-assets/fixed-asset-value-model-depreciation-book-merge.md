---
title: Modelo de valor e registro de depreciação de ativo fixo
description: 'Em versões anteriores, havia dois conceitos de avaliação para ativos fixos: modelos de valor e registros de depreciações. Na versão do Microsoft Dynamics 365 for Operations (1611), as funcionalidades modelo de valor e registro de depreciação foram mescladas em um único conceito que é conhecido como registro.'
author: moaamer
ms.date: 10/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e9d937211c049b2ec4ac06ac6eddce7fd9bcb5b0
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "8719989"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Modelo de valor de ativo fixo e mesclagem de registro de depreciações

[!include [banner](../includes/banner.md)]

Este tópico descreve o recurso do livro atual em Ativos fixos. Esse recurso baseia-se na funcionalidade anterior de modelo de valor que estava disponível em versões anteriores, mas também inclui todas as funcionalidade fornecidas anteriormente somente em registros de depreciação.

A funcionalidade do livro permite usar um único conjunto de páginas, consultas e relatórios para todos os processos de ativos fixos de sua organização. As tabelas deste tópico descrevem a funcionalidade anterior de registro de depreciação e modelo de valor com a funcionalidade atual para registros.

## <a name="setup"></a>Configuração
Por padrão, lançar registros de contabilidade (GL) e sub-razão de ativo fixo. Os registros têm uma nova opção **Lançar à contabilidade** que leva você a desabilitar os lançamentos na Contabilidade e lançar apenas na sub-razão de Ativo fixo. Essa funcionalidade é parecida com o comportamento anterior de lançamento de registro de depreciação. A configuração de nomes de diário possui um nível de lançamento nomeado Nenhum. Este nível de lançamento foi adicionado especificamente para transações de ativo fixo. Para lançar transações em registros que não são de Contabilidade, você deverá usar um nome de diário com o nível de lançamento definido como **Nenhum**.


| &nbsp;                                           | Registro de depreciações               | Método de depreciação                     | Registro (novo)                                              |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
| Lançar no livro Contabilidade                                   | Nunca                           | Sempre                          | Opção para lançar no livro Contabilidade                                |
| Níveis de lançamento                                   | Não aplicável                  | 3: Atual, operações e imposto | 11: Atual, operações, imposto, 7 camadas personalizadas e nenhum |
| Nomes de diário                                    | Nomes de diário de registro de depreciações | Contabilidade — nomes do diário              | Contabilidade — nomes do diário                                      |
| Registros derivados                                    | Não permitido                     | Permitido                         | Permitido                                                 |
| Substituir o perfil de depreciação para o ativo fixo | Permitido                         | Não permitido                     | Permitido                                                 |

## <a name="processes"></a>Processos
Agora os processos usam páginas comuns. Alguns processos são permitidas somente se **Lançar na contabilidade** a opção é **Não** definida na configuração de registro.

| &nbsp;                                           | Registro de depreciação               | Método de depreciação                     | Registro (novo)                                              |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
| Entrada de transação              | Diário do registro de depreciação | Diário de ativo fixo | Diário de ativo fixo                      |
| Depreciação extra             | Permitido                   | Não Permitido         | Permitido                                  |
| Excluir transações históricas | Permitido                   | Não Permitido         | Permitido, a menos que você esteja lançando na GL |
| Atualizações em massa                    | Permitido                   | Não Permitido         | Permitido, a menos que você esteja lançando na GL |

## <a name="inquiries-and-reports"></a>Consultas e relatórios
Consultas e relatórios suportam todos os registros. Relatórios que não são incluídos na tabela a seguir, anteriormente suportavam registros de depreciação e modelos de valor, e agora darão suporte a todos os tipos de registro. O campo **Nível de lançamento** também foi adicionado aos relatórios, para que você possa identificar facilmente os lançamentos de transação.

| &nbsp;                                           | Registro de depreciação               | Modelo de valor                     | Registro (novo)                                              |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
| Consultas                             | Transações do registro de depreciação | Transações de ativo fixo | Transações de ativo fixo |
| Demonstrativo de ativo fixo                 | Não permitido                    | Permitido                  | Permitido                  |
| Base de ativo fixo                     | Permitido                        | Não permitido              | Permitido                  |
| Aplicabilidade de ativo fixo na metade do trimestre | Permitido                        | Não permitido              | Permitido                  |

## <a name="upgrade"></a>Atualizar
O processo de atualização moverá suas configurações existentes e todas as transações existentes para a nova estrutura de registro. Os modelos de valor permanecerão como no momento, como um registro lançado na Contabilidade. Entretanto, os registros de depreciação serão movidos para um registro que tenha a opção **Lançar na Contabilidade** definido como **Não**. Os nomes de diário de registro de depreciação serão movidos a um nome de diário de Contabilidade com o nível de lançamento definido como **Não**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
