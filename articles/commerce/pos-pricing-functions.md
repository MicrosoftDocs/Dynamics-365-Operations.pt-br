---
title: Funções de definição de preços no PDV
description: Este artigo descreve várias funções de preço e desconto no aplicativo PDV (ponto de venda) do Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-14
ms.openlocfilehash: 210798ac192ee251594ec8ff9d23dab31ec2043e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473678"
---
# <a name="pricing-functions-in-pos"></a>Funções de definição de preços no PDV

[!include [banner](includes/banner.md)]

Este artigo descreve várias funções de preço e desconto no aplicativo PDV (ponto de venda) do Microsoft Dynamics 365 Commerce.

O aplicativo PDV do Dynamics 365 Commerce fornece recursos avançados que permitem que os trabalhadores de primeira linha executem operações de Store Commerce. A tabela a seguir mostra as funções de preço e desconto que estão disponíveis atualmente no aplicativo.

| Função                       | Operações de PDV |
|--------------------------------|----------------|
| Exibir preços                    | [Verificação de preço](#price-check) |
| Exibir descontos                 | [Exibir todos os descontos](#view-all-discounts)<br>[Exibir descontos disponíveis](#view-available-discounts) |
| Substituir preços                | [Substituição de preço](#price-override) |
| Aplicar ou remover descontos      | [Valor do Desconto de Linha](#line-discount-amount)<br>[Percentual do desconto de linha](#line-discount-percent)<br>[Valor do Desconto Total](#total-discount-amount)<br>[Percentual total de desconto](#total-discount-percent)<br>[Remover descontos do sistema da transação](#remove-system-discounts-from-transaction)<br>[Reaplicar descontos do sistema](#reapply-system-discounts) |
| Aplicar ou remover cupons        | [Adicionar código do cupom](#add-coupon-code)<br>[Remover código do cupom](#remove-coupon-code) |
| Calcular preços e descontos | [Recalcular](#recalculate) |

Para obter informações sobre como as operações anteriores podem ser configuradas no aplicativo PDV e se dão suporte ao modo off-line, consulte [Operações de ponto de venda (PDV) online e offline](pos-operations.md).

## <a name="price-check"></a>Verificação de preço

A operação **Verificação de preço** permite que os usuários do PDV pesquisem preços pré-configurados para um produto específico.

## <a name="view-all-discounts"></a>Exibir todos os descontos

A operação **Exibir todos os descontos** permite que os usuários do PDV pesquisem todas as promoções efetivas que estão sendo executadas atualmente no canal de armazenamento. Especificamente, esta operação lista todos os descontos que correspondem a qualquer uma das seguintes condições:

- O grupo de preços do desconto corresponde ao grupo de preços do armazenamento.
- O grupo de preços do desconto é mapeado para um programa de afiliação ou de fidelidade.
- O grupo de preços do desconto é mapeado para um catálogo associado à loja.

A operação **Exibir todos os descontos** mostra apenas descontos que não competem com nenhum desconto que já foi aplicado. Esse comportamento ajuda a garantir que, se um associado de vendas informar um cliente sobre um desconto e o cliente executar a ação necessária (por exemplo, o cliente compra mais um item para obter 10% desativado), o desconto será aplicado à transação. Os descontos baseados em cupom são mostrados somente se o parâmetro **Aplicar sem código de cupom** for ativado.

Na operação **Exibir todos os descontos** os usuários do PDV podem pesquisar descontos por nome e descrição e podem filtrar descontos com base no fato de exigirem um cupom.

## <a name="view-available-discounts"></a>Exibir descontos disponíveis

A operação **Exibir descontos disponíveis** permite que os usuários do PDV exibam todos os descontos aplicáveis a uma linha selecionada em uma transação ou para toda a transação. Os descontos aplicáveis a uma linha selecionada incluem descontos que já foram aplicados e descontos que ainda não foram aplicados, mas que podem ser aplicados (por exemplo, descontos combinados que exigem itens adicionais). Se um desconto aplicável estiver vinculado a um cupom no qual o parâmetro **Aplicar sem código de cupom** é ativado, o usuário do PDV também pode usar a função **Aplicar cupom** nessa operação para resgatar o cupom diretamente, sem precisar inserir ou digitalizar qualquer código de cupom ou códigos de barra de cupom.

## <a name="price-override"></a>Substituição de preço

A operação de **Substituição de preço** permite que os usuários do PDV substituam o preço de venda de um produto em uma transação. Esta operação funciona somente para produtos configurados para permitir substituições de preço.

## <a name="line-discount-amount"></a>Valor do Desconto de Linha

A operação **Valor do desconto de linha** permite que os usuários do PDV insiram um valor de desconto para um item de linha em uma transação. Esta operação se aplica apenas a itens descontáveis e respeita o **Valor máximo de desconto de linha** especificado no grupo de permissões de PDV do usuário.

## <a name="line-discount-percent"></a>Percentual do desconto de linha

A operação **Percentual do desconto de linha** permite que os usuários do PDV insiram uma porcentagem de desconto para um item de linha em uma transação. Esta operação se aplica apenas a itens descontáveis e respeita a **Porcentagem máxima de desconto de linha** especificada no grupo de permissões de PDV do usuário.

## <a name="total-discount-amount"></a>Valor do Desconto Total

A operação **Valor do desconto total** permite que os usuários do PDV insiram um valor de desconto para uma transação. Esta operação se aplica apenas a itens descontáveis e respeita o **Valor máximo total de desconto** especificado no grupo de permissões de PDV do usuário. Se o valor do desconto inserido exceder o valor máximo total de desconto, a operação será bloqueada e nenhum fluxo de substituição de permissão será disparado. No momento, não é possível aplicar um valor de desconto total a um carrinho que tem uma mistura de itens de vendas e itens de devolução.

## <a name="total-discount-percent"></a>Percentual total de desconto

A operação **Percentual total de desconto** permite que os usuários do PDV insiram uma porcentagem de desconto para uma transação. Esta operação se aplica apenas a itens descontáveis e respeita o valor da **Porcentagem total máxima de desconto** especificado no grupo de permissões de PDV do usuário. Se a porcentagem do desconto inserido exceder a porcentagem máxima total de desconto, a operação será bloqueada e nenhum fluxo de substituição de permissão será disparado. No momento, não é possível aplicar uma porcentagem de desconto total a um carrinho que tem uma mistura de itens de vendas e itens de devolução.

## <a name="remove-system-discounts-from-transaction"></a>Remover descontos do sistema da transação

A operação **Remover descontos do sistema da transação** permite que os usuários do PDV limpem todos os descontos do sistema aplicados (incluindo descontos baseados em cupom) de uma transação. Depois que essa operação for executada, o mecanismo de precificação começará a excluir os descontos do sistema do escopo de cálculo de desconto. A operação **Remover descontos do sistema da transação** não remove descontos manuais.

## <a name="reapply-system-discounts"></a>Reaplicar descontos do sistema

A operação **Reaplicar descontos do sistema** permite que os usuários do PDV reapliquem descontos calculados pelo sistema a uma transação, se os descontos foram removidos usando a operação **Remover descontos do sistema da transação**. Depois que essa operação for executada, o mecanismo de precificação começará a incluir todos os descontos do sistema no escopo de cálculo de desconto.

## <a name="add-coupon-code"></a>Adicionar código do cupom

A operação **Adicionar código do cupom** permite que os usuários do PDV adicionem um cupom a uma transação inserindo um código de cupom. Como alternativa, os usuários do PDV podem digitalizar um código de barras de cupom ou inseri-lo usando o teclado numérico na tela **Transações**.

## <a name="remove-coupon-code"></a>Remover código do cupom

A operação **Remover código do cupom** permite que os usuários do PDV selecionem e removam um ou mais cupons que estão aplicados atualmente a uma transação.

## <a name="recalculate"></a>Recalcular

A operação **Recalcular** permite que os usuários do PDV disparem o cálculo de definição de preços por demanda. Esta operação é necessária quando bloqueio de preço e/ou cálculo de preço atrasado é habilitado, e o usuário do PDV deseja recalcular os preços e os descontos após as alterações de carrinho ou da ordem. A operação **Recalcular** sempre recalcula toda a ordem. Ela não pode ser usada para recalcular linhas de venda selecionadas. Para aplicar descontos manuais a uma linha de venda bloqueada no PDV, os usuários do PDV devem primeiro usar a operação **Recalcular** para desbloquear todas as linhas de venda.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
