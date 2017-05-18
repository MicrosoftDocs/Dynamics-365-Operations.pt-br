---
title: "Ativos fixo, incluindo modelo de valor e registros de depreciações"
description: "Em versões anteriores, havia dois conceitos de avaliação para ativos fixos: modelos de valor e registros de depreciações. No Microsoft Dynamics 365 for Operations versão 1611, as funcionalidades de método de depreciação e de registro de depreciação foram mescladas em um único conceito que é conhecido como um registro."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 602515e9ea5681fd0bbe74525365b6628fee62d3
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Ativos fixo, incluindo modelo de valor e registros de depreciações

[!include[banner](../includes/banner.md)]


Em versões anteriores, havia dois conceitos de avaliação para ativos fixos: modelos de valor e registros de depreciações. No Microsoft Dynamics 365 for Operations versão 1611, as funcionalidades de método de depreciação e de registro de depreciação foram mescladas em um único conceito que é conhecido como um registro.

A funcionalidade de novo livro baseia-se em uma funcionalidade anterior de método de depreciação também inclui mas toda a funcionalidade que foi fornecida anteriormente somente em registros de depreciações. [![Registro como mesclagem da funcionalidade de método de depreciação e de registro de depreciação](./media/fixed-assets.png)](./media/fixed-assets.png) Em decorrência desta mesclagem, agora você pode usar um conjunto de páginas único, consultas e relatórios para todos os seus processos de ativo fixo. As tabelas deste tópico descrevem funcionalidades anterior de registros de depreciações, valor e modelos com a nova funcionalidade para registros.

## <a name="setup"></a>Instalação
Por padrão, lançar registros da contabilização (GL) e fixo sub-razão de ativo. Os registros têm uma nova opção **Lançar à contabilidade** que leva você a desabilitar os lançamentos ao GL e postar apenas na sub-razão de ativo fixo. Essa funcionalidade é parecido com o comportamento anterior de postagem de livros de depreciação. A configuração de nomes de diário possui um nível de lançamento que é chamado nenhum. Este nível de lançamento foi adicionado especificamente para transações de ativo fixo. Para lançar transações para os ativos que não são de GL, você deverá usar um nome a com o nível de lançamento definido **Não**.

|                                                  |                                 |                                 |                                                         |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
|                                                  | Registro de depreciações               | Método de depreciação                     | Registro (novo)                                              |
| Lançar no GL                                   | Nunca                           | Sempre                          | Opção para lançar ao GL                                |
| Níveis de lançamento                                   | Não Aplicável                  | 3: Atual, operações e imposto | 11: Atual, operações, imposto, 7 camadas personalizadas e nenhum |
| Nomes de diário                                    | Nomes de diário de registro de depreciações | GL - Nomes de diário              | GL - Nomes de diário                                      |
| Registros derivados                                    | Não permitido                     | Permitido                         | Permitido                                                 |
| Substituir o perfil de depreciação para o ativo fixo | Permitido                         | Não permitido                     | Permitido                                                 |

## <a name="processes"></a>Processos
Agora os processos usam páginas comuns. Alguns processos são permitidas somente se **Lançar na contabilidade** a opção é **Não** definida na configuração de registros.

|                                |                           |                     |                                          |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
|                                | Registro de depreciações         | Método de depreciação         | Registro (novo)                               |
| Entrada de transação              | Diário do registro de depreciações | Diário de ativo fixo | Diário de ativo fixo                      |
| Depreciação extra             | Permitido                   | Não Permitido         | Permitido                                  |
| Excluir transações históricas | Permitido                   | Não Permitido         | Reservado, a menos que esteja GL ao lançamento |
| Atualizações em massa                    | Permitido                   | Não Permitido         | Reservado, a menos que esteja GL ao lançamento |

## <a name="inquiries-and-reports"></a>Consultas e relatórios
Consultas e relatórios suportam todos os registros. Informa que não estiver na tabela a suporte aos registros de depreciação e métodos de depreciação, e agora continuará a dar suporte todos os tipos de registro. O campo **Nível de lançamento** também foi adicionado relatórios, para que você possa facilmente mais identificar as postagens de transação.

|                                       |                                |                          |                          |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
|                                       | Registro de depreciações              | Método de depreciação              | Registro (novo)               |
| Consultas                             | Transações do registro de depreciações | Transações de ativo fixo | Transações de ativo fixo |
| Demonstrativo de ativo fixo                 | Não permitido                    | Permitido                  | Permitido                  |
| Base de ativo fixo                     | Permitido                        | Não permitido              | Permitido                  |
| Aplicabilidade de ativo fixo na metade do trimestre | Permitido                        | Não permitido              | Permitido                  |

## <a name="upgrade"></a>Atualizar
O processo de atualização moverá suas configurações existentes e todas as transações existentes para a nova estrutura de registro. Os métodos de depreciação são permanecerá como momento, como um registro que lançar na contabilidade. Entretanto, os registros de depreciação serão movidos para um registro que tenha a opção **Lançar na contabilidade** definida como **Não**. Os nomes de diário de registro de depreciações serão movidos a um nome de diário da contabilidade com o nível de lançamento definido **Não**.




