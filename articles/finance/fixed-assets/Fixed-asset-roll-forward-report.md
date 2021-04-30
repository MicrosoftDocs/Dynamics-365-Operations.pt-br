---
title: Relatório de roll forward de ativo fixo
description: Este tópico explica como usar o relatório de roll forward de ativos fixos
author: saraschi2
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: b1693df7d535a340306d2b817ce008c292bad521
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897663"
---
# <a name="fixed-assets-roll-forward-report"></a>Relatório de roll forward de ativo fixo

[!include [banner](../includes/banner.md)]

O relatório **Relatório de roll forward de ativos fixos** fornece em um formato de leitura simples do Microsoft Excel, os dados de ativo fixo detalhados que você precisa para fechamento do período, demonstrativos financeiros e relatórios de imposto. O relatório incluir saldos inicial e final de ativos fixos, com movimentações de avaliação do período e novas aquisições do ativo e alienações que ocorreram durante o período. Os dados são relatados para ativos fixos individuais e os valores também são resumidos para grupos de ativos fixos e a entidade legal.

O relatório **Roll forward de ativos fixos** usa a estrutura de Relatório eletrônico (ER). Antes de executar o relatório, as configurações de roll-forward de Ativo fixo e do modelo de Ativos fixos devem ser importadas do Microsoft Dynamics Lifecycle Services (LCS). Para obter instruções, consulte [Baixar configurações do Relatório eletrônico no Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).

Este relatório estará disponível no Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, ou como um hotfix para Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Julho de 2017). Três hotfixes devem ser aplicados aos ambientes com a versão de julho de 2017:

- **KB 4041754:** A configuração de ER (relatório eletrônico) não pode ser baixada de LCS como não aplicável para a versão atual após a utilização do pacote de atualização da plataforma.
- **KB 4056107:** Atualização 5 cumulativa do relatório eletrônico (GER)
- **KB 4056353:** Relatórios de Demonstrativo e Observações dos ativos fixos não atendem aos requisitos no GAAP e no IFRS

A tabela a seguir descreve os campos disponíveis no relatório.


|                    Campo                    |                                                                                                                                descrição                                                                                                                                |
|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              Saldos: Iniciais              |                                                                                           O valor líquido contábil do ativo fixo a partir da data "inicial" especificada no relatório.                                                                                           |
|              Saldos: Fechamento              |                                                                                            O valor líquido contábil do ativo fixo a partir da data "final" especificada no relatório.                                                                                            |
|         Aquisições: Valor inicial         |                                                 A soma de todas as transações dos tipos de <strong>Aquisição</strong> e <strong>Ajuste de aquisição</strong> até a data "inicial" especificada no relatório.                                                  |
|      Aquisições: Aquisições do período      |                                                 A soma de todas as transações dos tipos de <strong>Aquisição</strong> e <strong>Ajuste de aquisição</strong> que foram contabilizadas durante o intervalo de datas do relatório.                                                  |
|       Aquisições: Alienações do período        |                                                                        A soma de todas as reversões de aquisição que foram postadas que tinham uma transação de alienação durante o intervalo de datas do relatório.                                                                        |
|         Aquisições: Valor de fechamento         |                                                  A soma de todas as transações dos tipos de <strong>Aquisição</strong> e <strong>Ajuste de aquisição</strong> até a data "final" especificada no relatório.                                                   |
|        Depreciações: Valor inicial         | A soma de todas as transações dos tipos de <strong>Depreciação</strong>, <strong>Ajuste de depreciação</strong>, <strong>Provisão para depreciação especial</strong> e <strong>Depreciação extraordinária</strong> até a data "inicial" especificada no relatório. |
|     Depreciações: depreciações do período     |                         A soma de todas as transações dos tipos de <strong>Depreciação</strong>, <strong>Ajuste de depreciação</strong> e <strong>Depreciação extraordinária</strong> que foram lançadas durante o intervalo de datas do relatório.                          |
| Depreciações: Depreciações especiais do período |                                                              A soma de todas as transações do tipo <strong>Provisão para depreciação especial</strong> que foram lançadas durante o intervalo de datas do relatório.                                                               |
|       Depreciações: Alienações do período       |                                                                       A soma de todas as reversões de depreciação que foram postadas que tinham uma transação de alienação durante o intervalo de datas do relatório.                                                                        |
|        Depreciações: Valor de fechamento         |  A soma de todas as transações dos tipos de <strong>Depreciação</strong>, <strong>Ajuste de depreciação</strong>, <strong>Provisão para depreciação especial</strong> e <strong>Depreciação extraordinária</strong> até a data "final" especificada no relatório.  |
|    Valorizações/Desvalorizações: Valor inicial     |                              A soma de todas as transações dos tipos de <strong>Ajuste de valorização</strong>, <strong>Ajuste de desvalorização</strong> e <strong>Reavaliação</strong> até a data "inicial" que é especificada no relatório.                               |
|   Valorizações/Desvalorizações: Valorizações do período   |                                                                    A soma de todas as transações do tipo <strong>Ajuste de valorização</strong> que foram lançadas durante o intervalo de datas do relatório.                                                                    |
|  Valorizações/Desvalorizações: Desvalorizações do período  |                                                                   A soma de todas as transações do tipo <strong>Ajuste de desvalorização</strong> que foram lançadas durante o intervalo de datas do relatório.                                                                   |
| Valorizações/Desvalorizações: Reavaliações do período  |                                                                        A soma de todas as transações do tipo <strong>Reavaliação</strong> que foram lançadas durante o intervalo de datas do relatório.                                                                        |
|   Valorizações/Desvalorizações: Alienações do período   |                                                           A soma de todos os estornos de valorizações, desvalorizações e reavaliações que foram lançadas que tinham uma transação de alienação durante o intervalo de datas do relatório.                                                           |
|    Valorizações/Desvalorizações: Valor de fechamento     |                               A soma de todas as transações dos tipos de <strong>Ajuste de valorização</strong>, <strong>Ajuste de desvalorização</strong> e <strong>Reavaliação</strong> até a data "final" que é especificada no relatório.                                |
|          Alienações: Data da alienação           |                                                                                                                A data de alienação do registro de ativos fixos.                                                                                                                |
|    Alienações: Valor líquido contábil na alienação    |                                                                                                    O valor líquido contábil do registro de ativos fixos no momento da alienação.                                                                                                    |
|            Alienações: Valor de venda            |                                                                                               O valor de venda para o registro de ativos fixos com uma alienação - transação de venda.                                                                                                |
|           Alienações: Valor de sucata            |                                                                                               O valor de sucata para o registro de ativos fixos com uma alienação - transação de sucata.                                                                                               |
|           Alienações: Lucros/perdas            |                                                                                 O valor de lucro ou perda calculado como parte da transação de alienação do registro de ativos fixos.                                                                                 |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]