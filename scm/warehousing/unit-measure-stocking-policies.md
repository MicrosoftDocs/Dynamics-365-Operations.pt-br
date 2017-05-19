---
title: "Unidade de medida e políticas de estoque"
description: "Este artigo descreve como as unidades padrão, as sequências de unidade e as conversões de unidade são usadas em processos de depósito."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDetails, EcoResProductDetailsExtended, EcoResStorageDimensionGroup, InventItemOrderSetup, UnitOfMeasureConversion, WHSRFMenuItem, WHSUOMSeqGroupTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29611
ms.assetid: 4b5ca875-9a06-416d-9ac0-cc3ab8f7338e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: b5ac0ae532765b7a934243c21008bae313dd80c0
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="unit-of-measure-and-stocking-policies"></a>Unidade de medida e políticas de estoque

[!include[banner](../includes/banner.md)]


Este artigo descreve como as unidades padrão, as sequências de unidade e as conversões de unidade são usadas em processos de depósito.

Os grupos de sequências de unidade definem a sequência de unidades que podem ser usadas em operações de depósito. São criados na página **Grupos de sequência de unidade**. A sequência mostra a relação das várias unidades. Por exemplo, você armazena os paletes que contêm as caixas, que contêm partes individuais de itens. Nesse caso, você deve fornecer as três diferentes unidades e a ordem lógica de camadas. Os grupos de sequências da unidade permitem definir políticas para o agrupamento de placas de licenças, e as unidades padrão que devem ser usadas para vários processos do depósito. Este artigo se aplica à solução de armazenamento avançado que está disponível no Gerenciamento de depósito e na solução de armazenamento mais básica que está disponível no Gerenciamento de estoque.

## <a name="unit-sequence-groups-for-released-products"></a>Grupos de sequências da unidade para produtos liberados
Se quiser usar produtos liberados nos processos de trabalho de depósito, um grupo de sequências da unidade deverá ser atribuído. Se você validar um produto que está associado a um Grupo de dimensões de armazenamento e a opção **Usar processos de gerenciamento de depósito** para o Grupo de dimensões de armazenamento for definida como **Sim**, você receberá uma mensagem de erro se uma ID de grupo de sequências da unidade não for definida para o produto. Se o grupo de sequências da unidade que você usa contiver várias linhas (e consequentemente várias unidades), você deverá configurar uma conversão de unidades entre as unidades. Você conclui esta configuração na página **Conversões de unidade**. A menor unidade em um grupo de sequências que você associa a um produto liberado deverá corresponder à unidade de estoque que é definida para o produto correspondente. A unidade de estoque é a unidade usada em cálculos de base do estoque disponível. Você também pode configurar as conversões de unidade de medida para variantes do produto de produtos mestre usando a opção **Habilitar as conversões de unidade de medida**.

## <a name="license-plate-grouping"></a>Agrupamento de placas de licença
Você pode especificar se os recebimentos menores ou maiores que uma unidade específica devem ser agrupados em uma placa de licença ou divididos em uma placa de licença separada para cada unidade. Para configurar esse comportamento, use a opção **Agrupamento de placa de licença** na guia **Detalhes da linha** da página **Grupos de sequências de unidade**. Se quiser usar o agrupamento de placas de licença quando processar o trabalho usando um dispositivo móvel, a opção **Agrupamento de placas de licença** deverá ser selecionada no item de menu **Dispositivo móvel**. Por exemplo, você está usando um dispositivo móvel para registrar um item associado a um grupo de sequências da unidade que tem duas linhas. A primeira linha é para Peças e a opção **Agrupamento da placa de licença** é definida como **Sim**. A segunda linha é para a unidade de Palete e a opção **Agrupamento de placas de licença** é definida como **Não**. Nesse caso, o sistema pode automaticamente orientar a separação e a criação de placas de licença com 100 peças.

## <a name="units-for-cycle-counting"></a>Unidades para contagem cíclica
Para definir quais unidades devem ser usadas como parte dos processos de contagem cíclica, selecione a opção **Usar unidade para contagem cíclica** na página **Grupos de sequências de unidade**. Você pode selecionar um máximo de quatro unidades no grupo de sequências. Se você selecionar mais de quatro unidades, as unidades adicionais não serão mostradas no dispositivo móvel.

## <a name="default-units-for-mobile-device-receiving-processes"></a>As unidades padrão para dispositivo móvel que recebe processos
Para definir as unidades padrão que devem ser usadas para processos de recebimento em dispositivos móveis, habilite as opções **Unidade padrão para compra e transferência** e **Unidade padrão para produção** na página **Grupos de sequências de unidade**. Por exemplo, você pode especificar que, por padrão, o sistema deve usar quantidades de Palete quando o estoque disponível da ordem de compra for recebido usando um dispositivo móvel, mas que a unidade de manutenção de estoque deve ser Peças. Para obter a conversão para o número de peças que cada palete contém, você deve definir uma conversão de unidades, como 100 peças = 1 Palete.

## <a name="default-order-settings"></a>Configurações Padrão da Ordem
Como parte da criação de produtos liberados, você deve selecionar unidades padrão para compras, vendas e estoque para processar as diversas ordens. Você pode definir as unidades e as quantidades padrão para vários documentos de origem usando as páginas **Configurações padrão da ordem** e **Configurações de ordem específicas do local**. Você pode acessar as páginas da página **Produtos liberados**.




