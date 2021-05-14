---
title: Testes de gerenciamento de qualidade
description: Este tópico descreve como criar testes que possam ser usados para ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b88011f486b6582db4727b85d021868899c6abe1
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956548"
---
# <a name="quality-management-tests"></a>Testes de gerenciamento de qualidade

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar testes que possam ser usados para ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.

Use a página **Testes** para definir e exibir os testes individuais que determinam se os seus produtos atendem às especificações de qualidade. Você pode atribuir um ou mais testes individuais a um grupo de teste. Nesse caso, você também pode especificar informações específicas, como os valores de medida aceitáveis. Os valores de medição são usados para testes quantitativos. Para testes qualitativos, são usadas variáveis de teste.

- Para testes quantitativos, o campo **Tipo** é definido como *Inteiro* ou *Fração*. Uma unidade de medida também é especificada. As especificações de qualidade e os resultados de teste são expressos em números.
- Para testes qualitativos, o campo **Tipo** é definido como *Opção*. Os testes qualitativos requerem informações adicionais sobre a variável de teste que está sendo medida e suas opções enumeradas. As especificações de qualidade e os resultados de teste são expressos de acordo com um resultado.

Opcionalmente, você pode atribuir um instrumento de teste a um teste. No entanto, os instrumentos de teste não são necessários para criar e usar testes com ordens de qualidade. Para obter mais informações, consulte [Instrumentos de teste de gerenciamento de qualidade](quality-test-instruments.md).

Você também pode especificar uma unidade para um teste, a fim de indicar a unidade de medida na qual os resultados do teste são registrados. Por exemplo, um teste de temperatura pode incluir uma unidade de graus Fahrenheit ou graus Celsius.

## <a name="example-of-a-test"></a>Exemplo de um teste

Uma empresa de fabricação realiza dois testes em material adquirido: um teste quantitativo para verificar a qualidade do material e um teste qualitativo para verificar se há danos na embalagem. A empresa especifica informações adicionais sobre o teste qualitativo para definir a variável de teste (por exemplo, embalagem danificada) e seus resultados. A empresa usa a página **Grupos de teste** para atribuir os dois testes a um grupo de testes e especificar informações específicas do teste. O grupo de teste é atribuído a uma ordem de qualidade, de modo que a empresa possa informar os resultados dos dois testes.

## <a name="create-a-test"></a>Criar um teste

Siga estas etapas para criar um teste.

1. Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Testes**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Teste** – Insira um nome ou uma ID exclusiva para o teste.
    - **Descrição** – Insira uma descrição detalhada do teste.
    - **Tipo** – Selecione o tipo de resultados que o teste produz. Para testes quantitativos, selecione *Fração* ou *Inteiro*. Para testes qualitativos, selecione *Opção*.
    - **Instrumento de teste** – Selecione um [instrumento de teste](quality-test-instruments.md) que deve ser usado para o teste.
    - **Unidade** – Se você selecionou *Fração* ou *Inteiro* no campo **Tipo** (ou seja, se o teste for um teste quantitativo), selecione a unidade de medida na qual os resultados do teste devem ser registrados.

1. Feche a página.

> [!NOTE]
> Depois de salvar um teste, não será mais possível editar o campo **Tipo** na grade. Se você precisar alterar o tipo de resultados de teste que serão registrados para um teste, selecione **Alterar tipo de teste de qualidade** no Painel de Ações. Na caixa de diálogo **Alterar tipo de teste de qualidade**, defina o campo **Novo tipo** como o tipo desejado e, em seguida, selecione **OK** para fechar a caixa de diálogo.

## <a name="additional-resources"></a>Recursos adicionais

- [Instrumentos de teste de gerenciamento de qualidade](quality-test-instruments.md)
- [Grupos de teste de gerenciamento de qualidade](quality-test-groups.md)
- [Variáveis de teste de gerenciamento de qualidade](quality-test-variables.md)
- [Associações de qualidade](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
