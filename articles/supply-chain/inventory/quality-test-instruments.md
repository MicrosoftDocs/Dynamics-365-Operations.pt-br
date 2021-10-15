---
title: Instrumentos de teste de gerenciamento de qualidade
description: Este tópico descreve como criar instrumentos de teste que possam ser usados para testes em ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d80a4f784a43e0d83d1f5b42f6740ef6da3add1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565894"
---
# <a name="quality-management-test-instruments"></a>Instrumentos de teste de gerenciamento de qualidade

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar instrumentos de teste que possam ser usados para testes em ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.

Use a página **Instrumentos de teste** para definir e exibir detalhes sobre os dispositivos usados para executar testes em ordens de qualidade. Os instrumentos de teste são opcionais. No entanto, eles podem ajudar os trabalhadores de qualidade a saber qual dispositivo ou ferramenta devem usar para executar um teste específico.

## <a name="test-instrument-example"></a>Exemplo de instrumento de teste

Você está executando vários testes em componentes elétricos. Alguns testes são para a saída de tensão dos componentes, um teste é para a temperatura e um teste é para o peso. Diferentes ferramentas, dispositivos ou equipamentos são usados para executar cada teste. Por exemplo, um voltímetro é usado para medir a tensão, um termômetro é usado para medir a temperatura e uma balança é usada para medir o peso. Você pode configurar cada um desses dispositivos como um instrumento de teste e indicar a unidade de medida na qual os resultados do teste devem ser registrados. Por exemplo, os resultados do voltímetro são registrados em volts, os resultados do termômetro são registrados em graus Fahrenheit ou graus Celsius e os resultados da balança são registrados em libras ou quilogramas.

## <a name="create-a-test-instrument"></a>Criar um instrumento de teste

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Instrumentos de teste**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Instrumento de teste** – Insira um nome ou uma ID exclusiva para o instrumento de teste.
    - **Descrição** – Insira uma descrição detalhada do instrumento de teste.
    - **Unidade** – Selecione a unidade na qual o instrumento mede os resultados. O campo **Precisão** é definido automaticamente com base na unidade selecionada.

1. Feche a página.

## <a name="additional-resources"></a>Recursos adicionais

- [Teste de gerenciamento de qualidade](quality-tests.md)
- [Grupos de teste de gerenciamento de qualidade](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
