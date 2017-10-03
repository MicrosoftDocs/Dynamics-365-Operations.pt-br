---
title: "Modelo de valor e registro de depreciação de ativo fixo"
description: "Em versões anteriores, havia dois conceitos de avaliação para ativos fixos: modelos de valor e registros de depreciações. Na versão do Microsoft Dynamics 365 for Operations (1611), as funcionalidades modelo de valor e registro de depreciação foram mescladas em um único conceito que é conhecido como registro."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: add41ceb1dd31d5b5aa26916114d7d7864cb1626
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---

# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Modelo de valor e registro de depreciação de ativo fixo

[!include[banner](../includes/banner.md)]


Em versões anteriores, havia dois conceitos de avaliação para ativos fixos: modelos de valor e registros de depreciações. Na versão do Microsoft Dynamics 365 for Operations (1611), as funcionalidades modelo de valor e registro de depreciação foram mescladas em um único conceito que é conhecido como registro.

A funcionalidade de novo livro baseia-se em uma funcionalidade anterior de modelo de valor, mas também inclui todas as funcionalidade fornecidas anteriormente somente em registros de depreciação. [![Registro como mesclagem da funcionalidade modelo de valor e registro de depreciação](./media/fixed-assets.png)](./media/fixed-assets.png) Em decorrência desta mesclagem, agora você pode usar um conjunto único de páginas, consultas e relatórios para todos os seus processos de ativo fixo. As tabelas deste tópico descrevem a funcionalidade anterior de registro de depreciação e modelo de valor com a nova funcionalidade para registros.

## <a name="setup"></a>Instalação
Por padrão, lançar registros de contabilidade (GL) e sub-razão de ativo fixo. Os registros têm uma nova opção **Lançar à contabilidade** que leva você a desabilitar os lançamentos na GL e lançar apenas na sub-razão de ativo fixo. Essa funcionalidade é parecida com o comportamento anterior de lançamento de registro de depreciação. A configuração de nomes de diário possui um nível de lançamento nomeado Nenhum. Este nível de lançamento foi adicionado especificamente para transações de ativo fixo. Para lançar transações em registros que não são de GL, você deverá usar um nome de diário com o nível de lançamento definido como **Nenhum**.

|                                                  |                                 |                                 |                                                         |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
|                                                  | Registro de depreciação               | Método de depreciação                     | Registro (novo)                                              |
| Lançar na GL                                   | Nunca                           | Sempre                          | Opção para lançar na GL                                |
| Níveis de lançamento                                   | Não Aplicável                  | 3: Atual, operações e imposto | 11: Atual, operações, imposto, 7 camadas personalizadas e nenhum |
| Nomes de diário                                    | Nomes de diário de registro de depreciação | GL - Nomes de diário              | GL - Nomes de diário                                      |
| Registros derivados                                    | Não permitido                     | Permitido                         | Permitido                                                 |
| Substituir o perfil de depreciação para o ativo fixo | Permitido                         | Não permitido                     | Permitido                                                 |

## <a name="processes"></a>Processos
Agora os processos usam páginas comuns. Alguns processos são permitidas somente se **Lançar na contabilidade** a opção é **Não** definida na configuração de registro.

|                                |                           |                     |                                          |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
|                                | Registro de depreciação         | Método de depreciação         | Registro (novo)                               |
| Entrada de transação              | Diário do registro de depreciação | Diário de ativo fixo | Diário de ativo fixo                      |
| Depreciação extra             | Permitido                   | Não Permitido         | Permitido                                  |
| Excluir transações históricas | Permitido                   | Não Permitido         | Permitido, a menos que você esteja lançando na GL |
| Atualizações em massa                    | Permitido                   | Não Permitido         | Permitido, a menos que você esteja lançando na GL |

## <a name="inquiries-and-reports"></a>Consultas e relatórios
Consultas e relatórios suportam todos os registros. Relatórios que não são incluídos na tabela a seguir, anteriormente suportavam registros de depreciação e modelos de valor, e agora darão suporte a todos os tipos de registro. O campo **Nível de lançamento** também foi adicionado aos relatórios, para que você possa identificar facilmente os lançamentos de transação.

|                                       |                                |                          |                          |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
|                                       | Registro de depreciação              | Modelo de valor              | Registro (novo)               |
| Consultas                             | Transações do registro de depreciação | Transações de ativo fixo | Transações de ativo fixo |
| Demonstrativo de ativo fixo                 | Não permitido                    | Permitido                  | Permitido                  |
| Base de ativo fixo                     | Permitido                        | Não permitido              | Permitido                  |
| Aplicabilidade de ativo fixo na metade do trimestre | Permitido                        | Não permitido              | Permitido                  |

## <a name="upgrade"></a>Atualizar
O processo de atualização moverá suas configurações existentes e todas as transações existentes para a nova estrutura de registro. Os modelos de valor permanecerão como no momento, como um registro lançado na contabilidade. Entretanto, os registros de depreciação serão movidos para um registro que tenha a opção **Lançar na contabilidade** definido como **Não**. Os nomes de diário de registro de depreciação serão movidos a um nome de diário de contabilidade com o nível de lançamento definido como **Não**.




