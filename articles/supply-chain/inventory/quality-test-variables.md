---
title: Variáveis de teste de gerenciamento de qualidade
description: Este artigo descreve como criar variáveis de teste que possam ser usadas para testes qualitativos em ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10fe206b76f2e50e09cb6aaa6055614c2fe9425d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857624"
---
# <a name="quality-management-test-variables"></a>Variáveis de teste de gerenciamento de qualidade

[!include [banner](../includes/banner.md)]

Este artigo descreve como criar variáveis de teste que possam ser usadas para testes qualitativos em ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.

Para cada teste qualitativo definido na página **Testes**, você deve definir uma variável de teste e seus possíveis resultados. (Para testes qualitativos, o campo **Tipo** na página **Testes** é definido como *Opção*.)

Use a página **Variáveis de teste** para configurar, editar e exibir os possíveis resultados de uma variável de teste associada a um teste qualitativo. Para cada resultado, você atribui um status de resultado *Aprovado* ou *Reprovado* para indicar se o teste é aprovado ou reprovado quando esse resultado é selecionado como resultado do teste. Use a página **Grupos de teste** para atribuir uma variável de teste e um resultado padrão a um teste qualitativo individual.

Para cada variável de teste, recomendamos que você defina pelo menos dois resultados: um que tenha o status de resultado *Aprovado* e um que tenha o status de resultado *Reprovado*. Não há limite para o número total de variáveis ou resultados que podem ser definidos. Além disso, vários testes podem usar as mesmas variáveis de teste para registrar os resultados.

## <a name="examples-of-test-variables"></a>Exemplos de variáveis de teste

### <a name="example-1"></a>Exemplo 1

Uma empresa de fabricação realiza dois testes em materiais fabricados. Em um teste, o nível de pH é associado a uma faixa colorida. Os níveis de pH aceitáveis aparecem em cores mais claras, e os níveis de pH inaceitáveis aparecem em cores mais escuras. Em outro teste, várias inspeções visuais são realizadas, e os trabalhadores de qualidade usam seu julgamento para determinar se o item é aprovado ou reprovado na inspeção visual.

### <a name="example-2"></a>Exemplo 2

Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado. Esse teste de inspeção tem várias variáveis. Uma variável é sabor, e os possíveis resultados para ela são: bom e ruim. Uma segunda variável é cor, e os possíveis resultados são: muito escura, muito clara e correta.

## <a name="create-a-test-variable"></a>Criar uma variável de teste

Siga estas etapas para criar uma variável de teste.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Variáveis de teste**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Variável** – Insira um nome ou uma ID exclusiva para a variável.
    - **Descrição** – Insira uma descrição detalhada da variável.

1. Enquanto a nova linha ainda estiver selecionada, selecione **Resultados** no Painel de Ações.
1. Na página **Resultados da variável de teste**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Resultado** – Insira um nome ou uma ID exclusiva para o resultado.
    - **Descrição** – Insira uma descrição detalhada do resultado.
    - **Status de resultado** – Selecione *Aprovado* ou *Reprovado* para indicar se o teste é aprovado ou reprovado quando o resultado é selecionado como resultado do teste.

1. Repita a etapa anterior para cada resultado adicional. Verifique se, pelo menos, um resultado tem o status de resultado *Aprovado* e se, pelo menos, um resultado tem o status *Reprovado*.
1. Feche as páginas.

## <a name="additional-resources"></a>Recursos adicionais

- [Instrumentos de teste de gerenciamento de qualidade](quality-test-instruments.md)
- [Testes de gerenciamento de qualidade](quality-tests.md)
- [Grupos de teste de gerenciamento de qualidade](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
