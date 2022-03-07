---
title: Balanceamento de lote
description: Este tópico descreve o processo de balanceamento de lote.
author: johanhoffmann
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMTable, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: a9e69b4d9213e57e5a920c7adda934ba845d17410c17d9c8a6356d717870ac23
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780067"
---
# <a name="batch-balancing"></a>Balanceamento de lote

[!include [banner](../includes/banner.md)]

Este tópico descreve como o processo de balanceamento de lote é suportado.

Para obter mais informações, assista ao [vídeo sobre balanceamento de lote](https://www.youtube.com/watch?v=4SNLWsU9KyI&feature=youtu.be).

No processo de balanceamento de lote, a quantidade de ingredientes a ser usada em um lote de produção é calculada a partir da concentração de princípios ativos em lotes de produto selecionados.

## <a name="products-that-have-an-active-ingredient"></a>Produtos com um princípio ativo

Um produto pode ser definido pela sua concentração de um princípio ativo. O princípio ativo de um produto é modelado usando um atributo de lote específico ao produto, que tem um valor mínimo, um valor máximo e um nível de destino.

O nível de destino de um atributo de lote representa a porcentagem prevista de um princípio ativo em um produto. Os valores mínimo e máximo representam o desvio aceito do nível de destino. Eles podem ser usados, por exemplo, como uma tolerância aceita para lotes no recebimento de produtos.

Um produto pode ter somente um princípio ativo. Para especificar o princípio ativo de um produto, primeiramente você deve definir um atributo de lote específico ao produto. Em seguida, você associa o atributo como um atributo base do produto.

No nível do produto, você também deve especificar como o nível do princípio ativo para um lote do produto deve ser registrado: como parte do processo de recebimento da compra ou como parte de um processo de ordem de qualidade.

Para associar um atributo base a um produto, a seguinte configuração é necessária:

- O produto deve ser controlado por lote. Para tornar um produto controlado por lote, você deve atribuir um grupo de dimensão de rastreamento ao produto que tem uma dimensão de lote ativa.

- O atributo que indica os níveis do ingrediente deve ser definido como um atributo de lote específico ao produto.

Para pesquisar e editar o valor real do princípio ativo de um lote:
1. Acesse **Gerenciamento de estoque \> Consultas e relatórios \> Dimensões de rastreamento \> Lotes**.
1. Selecione um número de lote na grade.
1. No painel de ações, abra a guia **Exibir** e selecione **Atributos de lote do estoque**.

## <a name="ingredient-types-and-how-they-interact-in-the-batch-balancing-process"></a>Tipos de ingrediente e como eles interagem no processo de balanceamento de lote

Uma linha de fórmula criada pode ter um destes tipos de ingrediente:

- Nenhum(a)
- Ativa
- Compensação
- Preenchedor

O resto desta seção fornece exemplos que mostram como cada tipo de ingrediente funciona. Os exemplos se baseiam na seguinte fórmula que tem um tamanho de lote total de 100 litros.

| Tipo de ingrediente | Nº de itens | Quantidade da linha de fórmula | Unidade |
|---|---|---|---|
| Nenhum(a) | A | 20 | Litro |
| Com atividade | E | 30 | Litro |
| Compensação | E | 10 | Litro |
| Preenchedor | B | 40 | Litro |

A tabela a seguir fornece uma visão geral dos resultados de cada exemplo.

| Nº de itens | Tipo de ingrediente | Quantidade prevista | Quantidade balanceada | Quantidade ativa | Unidade | Valor base |
|---|---|---|---|---|---|---|
| A | Nenhum(a) | 20 | 20 | | Litro | |
| B | Ativa | 30 | 25,71 | 9:00 | Litro | 30.00 |
| E | Compensação | 10 | 14.72 | | Litro | |
| B | Preenchedor | 40 | 39.57 | | Litro | |

### <a name="active-ingredients"></a>Princípios ativos

Quando um produto com um atributo base é adicionado a uma linha de fórmula, é conhecido como um *princípio ativo* da fórmula. Ordens de lote que possuem fórmulas com princípios ativos podem ser usadas para o processo de balanceamento de lote. Para cada ingrediente da fórmula, o processo de balanceamento de lote estima a quantidade necessária para produzir o produto. A estimativa das quantidades se baseia na concentração de princípios ativos nos lotes selecionados.

#### <a name="active-ingredient-example"></a>Exemplo de princípio ativo

O ingrediente B possui atributo base X e nível de destino 30, e faz parte de uma fórmula que requer 30 litros do ingrediente B para cada 100 litros do produto. É criada uma ordem de lote com um tamanho de lote de 100 litros. A ordem de lote é iniciada, e durante o processo de balanceamento de lote, o usuário seleciona um lote do ingrediente B que possui nível de concentração 35. Como o nível de concentração é 35 e, portanto, maior do que o nível de destino, que é 30, a quantidade balanceada do ingrediente B é reduzida usando o índice do valor de concentração para o nível de destino do lote, que é multiplicado pela quantidade prevista. O cálculo da quantidade balanceada tem a seguinte aparência:

(30 ÷ 35) × 30 litros = 25,71 litros

### <a name="none-ingredients"></a>Princípio do tipo Nenhum

Ao aplicar o processo de balanceamento de lote quando o **Tipo de princípio** é *Nenhum*, a quantidade prevista e a quantidade balanceada da linha de fórmula na ordem do lote são iguais.

#### <a name="none-ingredient-example"></a>Exemplo de princípio ativo do tipo Nenhum

O ingrediente A é atribuído a um ingrediente do tipo *Nenhum* e adicionado a uma fórmula para um produto finalizado. A fórmula requer 10 litros do ingrediente A para cada 100 litros do produto finalizado. Quando uma ordem de lote requer 200 litros, a quantidade prevista e a quantidade balanceada do ingrediente A são calculadas como 20 litros.

### <a name="compensating-ingredients"></a>Ingredientes de compensação

Um ingrediente de compensação pode compensar ou complementar o efeito do princípio ativo em um produto. Portanto, a quantidade de um ingrediente de compensação consumido depende da concentração do produto:

- **Efeito de oposição** – Se a quantidade do princípio ativo for maior do que a esperada, você deverá diminuir a quantidade do ingrediente de compensação.

- **Efeito complementar** – Se a quantidade do princípio ativo for menor do que a esperada, você deverá aumentar a quantidade do ingrediente de compensação.

A relação entre um princípio ativo e um ingrediente complementar é configurada na página **Princípio de compensação**.

Siga estas etapas para configurar as relações entre ingredientes.

1. Selecione **Gerenciamento de informações de produto \> Listas, materiais e fórmulas \> Fórmulas**.
1. Abra uma linha da fórmula e selecione **Ingredientes** para abrir a página **Princípio de compensação**.
1. Selecione a linha que representa um princípio de compensação e, em seguida, selecione o princípio ativo para compensar.

No princípio de compensação, você também insere um fator de compensação positivo ou negativo para especificar para quanto compensar, e se o princípio deve ser de oposição ou complementar. Um fator positivo indica um efeito complementar, e um fator negativo indica um efeito de oposição.

#### <a name="compensating-ingredient-example"></a>Exemplo de ingrediente de compensação

O ingrediente B é um princípio ativo com atributo base X e nível de destino 30. Está incluído em uma fórmula que requer 30 litros do ingrediente B para cada 100 litros do produto. O ingrediente C é um ingrediente de compensação, e uma quantidade 10 está incluída na mesma fórmula. Um fator de compensação de 1,10 é configurado para o princípio de compensação. Portanto, a quantidade balanceada do ingrediente de compensação será reduzida pela diferença entre a quantidade balanceada do princípio ativo e a quantidade necessária prevista multiplicada por 1,10.

No exemplo do tipo de ingrediente *Ativo*, a quantidade balanceada do princípio ativo necessário foi calculada como 25,71, e a quantidade necessária prevista foi calculada como 30. Nesse caso, a quantidade balanceada do ingrediente de compensação será calculada desta forma:

1. A diferença entre a quantidade prevista e a quantidade balanceada é determinada:  
    25,71 – 30 = –4,29

1. O resultado é multiplicado pelo fator de compensação:  
    4,29 × 1,10 = –4,72

1. A quantidade de compensação prevista é reduzida em –4,72 para determinar a quantidade de compensação balanceada:  
    10 – (–4,72) = 14,72

Como 1,10 é um fator de compensação positivo, esse princípio de compensação tem um efeito complementar. Nesse caso, o princípio ativo é mais concentrado do que o esperado. Portanto, é necessária uma quantidade maior do ingrediente de compensação.

### <a name="filler-ingredients"></a>Excipientes

Um *excipiente* é um ingrediente neutro usado para alcançar a quantidade de saída desejada do produto finalizado. Os ajustes nas quantidades de excipientes são calculados com base em variações no princípio ativo e no ingrediente de compensação comparadas à quantidade padrão.

#### <a name="filler-ingredient-example"></a>Exemplo de excipiente

Você formulou um produto que inclui os ingredientes A, B, C e D para um tamanho de fórmula de 100 litros. Você calculou a quantidade balanceada de todos os tipos de ingrediente exceto do *Excipiente*, que é usado em uma linha.
A quantidade balanceada do excipiente é calculada como a diferença entre o tamanho do lote de 100 litros e a soma dos ingredientes A, B e C:

100 – (20 + 25,71 + 14,72) = 39,57

## <a name="the-batch-balancing-process"></a>O processo de balanceamento de lote

O processo de balanceamento de lote é executado da página **Balanceamento de lote**.
Selecione **Gerenciamento de custo \> Ordens de lote** e, em seguida, na guia **Processo**, selecione **Balanceamento de lote**. O balanceamento de lote está disponível para ordens de lote que possuam um status **Iniciado**.

Em geral, o balanceamento de lote pode ser aplicado a ordens de lote se a fórmula tiver pelo menos uma linha de fórmula em que o **Tipo de princípio** seja *Ativo*. (Para conhecer a exceção a essa regra, consulte a seção “Ordens de lote não aplicáveis ao balanceamento de lote” posteriormente neste tópico.)

O processo de balanceamento de lote pode ser dividido em dois subprocessos:

1. Balancear ingredientes do lote
1. Confirmar e liberar a fórmula

### <a name="balance-batch-ingredients"></a>Balancear ingredientes do lote

No subprocesso Balancear ingredientes do lote, a quantidade de ingredientes a ser usada no lote de produção é calculada com base nos lotes selecionados que têm princípios ativos. Geralmente, o cálculo só pode ser concluído se houver cobertura completa de todos os ingredientes. Você não pode balancear somente parte do lote que a ordem de lote está configurada para produzir.

> [!NOTE]
> Você não pode salvar um cálculo e concluir o processo de balanceamento de lote depois. Se você fechar a página **Balanceamento de lote**, deverá repetir o cálculo para concluir o processo.

### <a name="confirm-and-release-the-formula"></a>Confirmar e liberar a fórmula

Depois que as quantidades dos ingredientes forem calculadas, você poderá confirmar e liberar a fórmula. O processo de liberação difere, dependendo de os produtos estarem habilitados ou não para os processos de gerenciamento de depósito:

- Se um produto estiver habilitado para os processos de gerenciamento de depósito, a linha de fórmula será liberada para o depósito de acordo com os princípios dos processos de gerenciamento de depósito. A linha de fórmula é liberada em quantidades correspondentes às quantidades balanceadas e para os lotes específicos que são selecionados para os princípios ativos.

    > [!NOTE]
    > As linhas de fórmula podem ser liberadas para o depósito somente como parte do processo de balanceamento de lote. Embora haja outras opções para liberar materiais de produção para o depósito, essas opções não podem ser usadas para linhas de fórmula.

- Se um produto não estiver habilitado para os processos de gerenciamento de depósito, uma lista de separação de produção será criada para o produto quando você confirmar e liberar a fórmula.

Em uma única fórmula, você pode combinar os produtos habilitados e os produtos não habilitados para os processos de gerenciamento de depósito. Quando os dois tipos de produtos são incluídos em uma fórmula, os produtos habilitados para os processos de gerenciamento de depósito são liberados para o depósito. Para os produtos não habilitados para os processos de gerenciamento de depósito, uma lista de separação será criada quando a fórmula for confirmada e liberada.

### <a name="batch-orders-that-arent-applicable-for-batch-balancing"></a>Ordens de lote não aplicáveis ao balanceamento de lote

Há duas exceções à regra de que as ordens de lote são aplicáveis ao balanceamento de lote se a fórmula tiver pelo menos uma linha de fórmula em que o **Tipo de ingrediente** seja *Ativo*.

1. Se uma fórmula contiver um princípio ativo para um produto habilitado para os processos de gerenciamento de depósito, mas o número de lote estiver abaixo da localização na hierarquia de reservas, a ordem de lote não será aplicável ao balanceamento de lote.
1. Se a unidade de medida da fórmula for diferente da unidade de medida do estoque do princípio ativo, a ordem de lote não será aplicável ao balanceamento de lotes.

Uma ordem de lote não aplicável ao balanceamento de lote passa pelo ciclo de processo normal para ordens de lote.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]