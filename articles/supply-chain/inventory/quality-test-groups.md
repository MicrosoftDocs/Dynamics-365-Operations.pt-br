---
title: Grupos de teste de gerenciamento de qualidade
description: Este tópico descreve como criar grupos de teste para que vários testes possam ser usados com ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdd7c2eb452d7d34e05d9e067e61d6587e1fd4b67b22723ecef2832501be1eaf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774117"
---
# <a name="quality-management-test-groups"></a>Grupos de teste de gerenciamento de qualidade

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar grupos de teste para que vários testes possam ser usados com ordens de qualidade no Microsoft Dynamics 365 Supply Chain Management.

Use a página **Grupos de teste** para configurar, editar e exibir grupos de teste e os testes individuais atribuídos a eles. A parte superior da página mostra os grupos de teste e a parte inferior mostra os testes atribuídos a um grupo de teste selecionado.

Você atribui várias políticas a um grupo de teste, como um plano de amostragem, um nível de qualidade aceitável (AQL) e o requisito para testes destrutivos. Em seguida, ao atribuir um teste individual a um grupo de teste, você define informações adicionais, como a sequência, os documentos e as datas de validade. Para um teste quantitativo, as informações que você define também incluem os valores de medida aceitáveis. Para um teste qualitativo, as informações incluem a variável de teste e o resultado padrão.

O grupo de testes atribuído a uma ordem de qualidade define o conjunto padrão de testes que devem ser realizados no item específico. No entanto, você pode adicionar, excluir ou alterar os testes da ordem de qualidade. Os resultados do teste são relatados para cada teste em uma ordem de qualidade.

Ao definir um grupo de teste, você pode, opcionalmente, especificar uma amostragem de item. As amostragens de item são usadas para definir o valor do produto que deve ser testado. Para obter mais informações, consulte [Amostragem de item de gerenciamento de qualidade](quality-item-sampling.md). Você também pode indicar se os testes em um grupo de teste são destrutivos. Em um teste destrutivo, a amostragem de item é destruída e a quantidade é removida do estoque disponível.

## <a name="example-of-a-test-group"></a>Exemplo de um grupo de teste

Uma fábrica define um grupo de testes para cada variação de suas diretrizes de qualidade. Os vários grupos de testes refletem diferenças nos planos de amostragem, nos conjuntos de testes que precisam ser executados juntos, na AQL, e em outros fatores. Para testes quantitativos, também existem diferenças nos valores de medida aceitáveis. Para aplicar suas diretrizes de qualidade, a empresa atribui um grupo de teste a cada regra usada para gerar automaticamente ordens de qualidade na página **Associações de qualidade**. Ela também atribui um grupo de teste a ordens de qualidade criadas manualmente.

## <a name="create-a-test-group"></a>Criar um grupo de teste

Para criar um grupo de teste, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de teste**.
1. No Painel de Ações, selecione **Novo** para adicionar uma linha à grade na parte superior da página. Defina os seguintes campos para a nova linha:

    - **Grupo de teste** – Insira um nome ou uma ID exclusiva para o grupo de teste.
    - **Descrição** – Insira uma descrição detalhada do grupo de teste.
    - **Nível de qualidade aceitável** – Insira a porcentagem total de resultados de teste que devem ser aprovados para que o grupo de testes seja considerado aprovado.
    - **Amostragem de item** – Selecione uma amostragem de item. Para obter mais informações, consulte [Amostragem de item de gerenciamento de qualidade](quality-item-sampling.md).
    - **Destrutivo** – Marque esta caixa de seleção para indicar que o grupo de teste destruirá os itens testados.

1. Enquanto a nova linha ainda estiver selecionada, selecione a guia **Geral** na parte superior da página. Algumas das configurações do grupo de teste selecionado na guia **Visão geral** são repetidas aqui. Além disso, você pode definir os seguintes campos para o grupo:

    - **Atualizar atributo de lote do estoque** – Quando você definir esta opção como *Sim* aqui, ela será automaticamente definida como *Sim* para cada novo teste adicionado ao grupo de teste na parte inferior da página.
    - **Atualizar disposição em lotes** – Quando você definir esta opção como *Sim*, se o item que está sendo testado for controlado por lote, a disposição do lote será atualizada automaticamente com o valor selecionado no campo **Disposição em lotes da ordem de qualidade reprovada** ou **Disposição em lotes da ordem de qualidade aprovada**.
    - **Disposição em lotes da ordem de qualidade reprovada** – Selecione o código de disposição em lotes que deve ser atribuído quando uma ordem de qualidade que inclui esse grupo de teste for reprovada porque não atende ao AQL.
    - **Disposição em lotes da ordem de qualidade aprovada** – Selecione o código de disposição em lotes que deve ser atribuído quando uma ordem de qualidade que inclui esse grupo de teste for aprovada porque atende ao AQL.
    - **Atualizar status do estoque** – Quando você definir esta opção como *Sim*, se **Status do estoque** estiver habilitado no grupo de dimensões de armazenamento do item que está sendo testado, o status será atualizado automaticamente com o status selecionado no campo **Status da ordem de qualidade reprovada** ou **Status da ordem de qualidade aprovada**.
    - **Status da ordem de qualidade reprovada** – Selecione o status de estoque que deve ser atribuído ao item quando uma ordem de qualidade que inclui esse grupo de teste for reprovada porque não atende ao AQL.
    - **Status da ordem de qualidade aprovada** – Selecione o status de estoque que deve ser atribuído ao item quando uma ordem de qualidade que inclui esse grupo de teste for aprovada porque atende ao AQL.

## <a name="add-a-qualitative-test-to-a-test-group"></a>Adicionar um teste qualitativo a um grupo de teste

Para adicionar um teste qualitativo a um grupo de teste, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de teste**.
1. Na guia **Visão geral** na parte superior da página, selecione o grupo de teste ao qual você deseja adicionar um teste.
1. Na parte inferior da página, na guia **Visão geral**, selecione **Adicionar** na barra de ferramentas para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Número de sequência** – Insira um número inteiro para especificar a ordem em que os testes devem ser realizados. Os testes com números de sequência menores serão executados antes dos testes com números de sequência maiores.

        > [!NOTE]
        > É recomendável deixar um intervalo entre os números de sequência. Por exemplo, defina o campo **Número de sequência** como *10* para o primeiro teste e, em seguida, aumente o valor em 10 para cada teste adicional. Dessa forma, você pode adicionar novos testes posteriormente sem ter que excluir e recriar as linhas para colocá-las na ordem desejada.

    - **Teste** – Selecione o teste que deseja realizar. Para um teste qualitativo, selecione um teste em que o campo **Tipo** esteja definido como *Opção*.
    - **Vigência** – Selecione a primeira data em que o teste é válido. Se você deixar esse campo em branco, não haverá limite.
    - **Validade** – Selecione a última data em que o teste é válido. Se você deixar esse campo em branco ou defini-lo como *Nunca*, não haverá limite.
    - **Determinação de valor de teste** – Selecione como um AQL deve ser determinado quando vários resultados forem registrados para o mesmo teste. Para um teste qualitativo, só é possível selecionar *Manual*. Se você selecionar um dos outros valores (*Média*, *Mínimo* ou *Máximo*), receberá uma mensagem de erro ao salvar o grupo de teste.
    - **Atributo** – Se você quiser registrar os resultados do teste em um atributo de lote, selecione o atributo aqui e marque a caixa de seleção **Atualizar atributo de lote do estoque**.
    - **Atualizar atributo de lote do estoque** – Marque esta caixa de seleção para registrar os resultados do teste para o atributo de lote selecionado no campo **Atributo**.

1. Na parte inferior da página, selecione a guia **Geral**. Algumas das configurações do teste selecionado na guia **Visão geral** são repetidas aqui. Além disso, você pode definir os seguintes campos para o teste:

    - **Certificado de relatório de análise** – Defina esta opção como *Sim* para indicar que os resultados do teste devem ser impressos no certificado de análise (CoA). Esse relatório pode ser gerado com base na ordem de qualidade.
    - **Ação em caso de erro** – Selecione *Aceitar* ou *Falhar* para indicar se o teste deve ser aprovado ou reprovado se o AQL dele não for atendido.
    - **Nível de qualidade aceitável** – Insira a porcentagem total de resultados de teste que devem ser aprovados para que o teste seja considerado aprovado.

1. Na parte inferior da página, na guia **Teste**, defina os seguintes campos:

    - **Variável** – Selecione a variável de teste para a qual registrar os resultados do teste qualitativo.
    - **Resultado padrão** – Selecione o resultado padrão que deve ser registrado para os resultados do teste.
    - **Instrumento de teste** – Selecione o dispositivo que deve ser usado para o teste. Se um instrumento de teste for definido, ele será inserido automaticamente para o teste no grupo de teste.

1. Feche a página.

## <a name="add-a-quantitative-test-to-a-test-group"></a>Adicionar um teste quantitativo a um grupo de teste

Para adicionar um teste quantitativo a um grupo de teste, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de teste**.
1. Na guia **Visão geral** na parte superior da página, selecione o grupo de teste ao qual você deseja adicionar um teste.
1. Na parte inferior da página, na guia **Visão geral**, selecione **Adicionar** na barra de ferramentas para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Número de sequência** – Insira um número inteiro para especificar a ordem em que os testes devem ser realizados. Os testes com números de sequência menores serão executados antes dos testes com números de sequência maiores.

        > [!NOTE]
        > É recomendável deixar um intervalo entre os números de sequência. Por exemplo, defina o campo **Número de sequência** como *10* para o primeiro teste e, em seguida, aumente o valor em 10 para cada teste adicional. Dessa forma, você pode adicionar novos testes posteriormente sem ter que excluir e recriar as linhas para colocá-las na ordem desejada.

    - **Teste** – Selecione o teste que deseja realizar. Para um teste quantitativo, selecione um teste em que o campo **Tipo** esteja definido como *Fração* ou *Inteiro*.
    - **Vigência** – Selecione a primeira data em que o teste é válido. Se você deixar esse campo em branco, não haverá limite.
    - **Validade** – Selecione a última data em que o teste é válido. Se você deixar esse campo em branco ou defini-lo como *Nunca*, não haverá limite.
    - **Determinação de valor de teste** – Selecione como um AQL deve ser determinado quando vários resultados forem registrados para o mesmo teste. As opções disponíveis são *Média*, *Mínimo*, *Máximo* e *Manual*.
    - **Atributo** – Se você quiser registrar os resultados do teste em um atributo de lote, selecione o atributo aqui e marque a caixa de seleção **Atualizar atributo de lote do estoque**.
    - **Atualizar atributo de lote do estoque** – Marque esta caixa de seleção para registrar os resultados do teste para o atributo de lote selecionado no campo **Atributo**.

1. Na parte inferior da página, selecione a guia **Geral**. Algumas das configurações do teste selecionado na guia **Visão geral** são repetidas aqui. Além disso, você pode definir os seguintes campos para o teste:

    - **Certificado de relatório de análise** – Defina esta opção como *Sim* para indicar que os resultados do teste devem ser impressos no CoA. Esse relatório pode ser gerado com base na ordem de qualidade.
    - **Ação em caso de erro** – Selecione *Aceitar* ou *Falhar* para indicar se o teste deve ser aprovado ou reprovado se o AQL dele não for atendido.
    - **Nível de qualidade aceitável** – Insira a porcentagem total de resultados de teste que devem ser aprovados para que o teste seja considerado aprovado.

1. Na parte inferior da página, na guia **Teste**, defina os seguintes campos:

    - **Padrão** – Insira o valor (inteiro ou fração) esperado para os resultados do teste. Esse valor será inserido por padrão nos resultados do teste. Além disso, ele será inserido automaticamente como um valor padrão nos campos **Mín.** e **Máx.**.
    - **Mín.** – Insira o valor mínimo permitido para os resultados do teste. O valor inserido deve ser menor do que o valor definido no campo **Padrão**. Quando você atualiza o campo **Mín.**, o campo **Tolerância mín. (%)** é atualizado automaticamente. Da mesma forma, quando você atualiza o campo **Tolerância mín. (%)**, o campo **Mín.** é atualizado automaticamente.
    - **Máx.** – Insira o valor máximo permitido para os resultados do teste. O valor inserido deve ser maior do que o valor definido no campo **Padrão**. Quando você atualiza o campo **Máx.**, o campo **Tolerância máx. (%)** é atualizado automaticamente. Da mesma forma, quando você atualiza o campo **Tolerância máx. (%)**, o campo **Máx.** é atualizado automaticamente.
    - **Instrumento de teste** – Selecione o dispositivo que deve ser usado para o teste. Se um instrumento de teste for definido, ele será inserido automaticamente para o teste no grupo de teste.

1. Feche a página.

## <a name="additional-resources"></a>Recursos adicionais

- [Instrumentos de teste de gerenciamento de qualidade](quality-management-processes.md)
- [Testes de gerenciamento de qualidade](quality-management-processes.md)
- [Variáveis de teste de gerenciamento de qualidade](quality-management-processes.md)
- [Associações de qualidade](quality-management-processes.md)
- [Atributos de lote](/supply-chain/production-control/batch-attributes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
