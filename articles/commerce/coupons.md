---
title: Cupons
description: Este artigo fornece uma visão geral de recursos relacionados a cupom no Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-30
ms.openlocfilehash: 20427a04a552ddec013daa6576ec64ab7046e95f
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709750"
---
# <a name="coupons"></a>Cupons

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral de recursos relacionados a cupom no Microsoft Dynamics 365 Commerce.

Os cupons são códigos e códigos de barras usados ​​para adicionar descontos às transações. Os varejistas distribuem cupons para clientes potenciais ou existentes para ajudar a melhorar o reconhecimento da marca, a conversão da unidade, manter a base de clientes, aumentar as vendas e acabar aumentando a receita. Os cupons se tornaram uma das ferramentas de marketing mais populares e são uma nova norma em vendas de comércio eletrônico.

No Dynamics 365 Commerce, os cupons são vinculados a descontos e são considerados validação adicional além dos descontos. Cada cupom está relacionado a um desconto e o desconto vinculado define o conjunto de produtos para os quais o cupom é válido.

Os grupos de preços associados a um desconto definem as condições qualificadas para as quais um cupom pode ser usado. Essas condições incluem grupos de clientes e canais de vendas. Os cupons também fornecem as propriedades **Limite de uso** e **Cliente necessário** que podem ser usadas para configurar restrições de uso opcional.

Cada cupom pode ter vários códigos de cupom e códigos de barras de cupom, e cada código pode ter seu próprio intervalo de datas efetivo e status. Se o status de um código estiver definido como **Inativo**, o código não poderá ser usado em nenhum canal.

## <a name="set-up-a-coupon"></a>Configurar um cupom

Antes de configurar um cupom, você deve configurar o código da barra de cupom e duas sequências de números de cupom.

Para configurar um cupom no Commerce headquarters, siga estas etapas:

1. Acesse **Varejo e Comércio \> Gerenciamento de estoque \> Códigos de barras e etiquetas \> Caracteres de máscara**.
1. Selecione **Adicionar** para criar um caractere de máscara do tipo **Código de cupom**. No campo **Caractere**, você pode selecionar qualquer caractere não usado.
1. Acesse **Varejo e Comércio \> Gerenciamento de estoque \> Códigos de barras e etiquetas \> Configuração da máscara do código de barras**.
1. Selecione **Novo** para criar uma máscara do código de barras do tipo **Cupom**.
1. Acesse **Varejo e Comércio \> Gerenciamento de estoque \> Códigos de barras e etiquetas \> Configuração do código de barras**.
1. Selecione **Novo** para criar um código de barras que usa a máscara de código de barras que você criou.
1. Vá para **Administração da organização \> Sequências numéricas**.
1. Crie duas sequências numéricas:

    1. Uma sequência para a referência **Número do cupom**. Essa sequência define o identificador exclusivo do cupom.
    1. Uma sequência para a referência **ID do código do cupom**. Esta sequência define o identificador exclusivo de cada código de cupom para um cupom.

    Para ambas as sequências numéricas, você deve definir o campo **Escopo** como **Empresa**. Na maioria dos casos, os números sequenciais devem ser gerados automaticamente.

1. Vá para **Parâmetros do Commerce \> Preços e descontos \> Cupons**.
1. Defina o campo **Máscara do código de barras do cupom** como o código de barras criado anteriormente.
1. Vá para **Configurar parâmetros \> Sequências numéricas**.
1. Selecione as sequências numéricas criadas anteriormente para as referências de **Número do cupom** e **ID do código do cupom**.

Para configurar um cupom, você deve criar o desconto e o cupom separadamente, e vinculá-los selecionando o desconto no campo **Desconto** da configuração do cupom. Depois que um cupom é vinculado a um desconto, os campos **Status**, **Data de efetivação** e **Data de vencimento** do desconto vinculado se tornam somente leitura porque os valores são determinados pelo status e pelo período de validade do cupom. Quando o status de um cupom é definido como **Ativo**, o status do desconto vinculado é automaticamente atualizado para **Habilitado**. Da mesma forma, quando o status de um cupom é definido como **Inativo**, o status do desconto vinculado é automaticamente atualizado para **Desabilitado**.

## <a name="use-a-coupon"></a>Usar um cupom

Para adicionar um cupom a uma transação de venda no ponto de venda (PDV) do Commerce, você pode usar um código do cupom ou um código de barras do cupom. Para usar um código de cupom, selecione a operação **Adicionar código de cupom** e insira o código. Para usar um código de barras do cupom, você pode digitalizar o código de barras usando um dispositivo de digitalização ou inseri-lo usando o teclado numérico na tela **Transação**.

Às vezes, os varejistas desejam que os caixas possam dar descontos de valor fixo aos clientes por motivos de Appeasement ou por causa de defeitos de produtos, mas não desejam imprimir códigos de cupom e distribuí-los aos caixas. Nesse caso, você pode definir a opção **Aplicar sem código de cupom** para o cupom como **Sim**. Os caixas de PDV podem usar a função **Aplicar cupom** na operação **Exibir descontos disponíveis** para adicionar um cupom a uma transação sem inserir manualmente o código. Se existirem vários códigos de cupom para um cupom, o sistema selecionará automaticamente o primeiro código ativo e o aplicará na transação.

Para adicionar um cupom a uma ordem de venda de call center, um usuário do call center deve selecionar **Cupons** na guia **Gerenciar** do Painel de Ações na página ordem de venda.

Para adicionar um cupom a uma ordem de comércio eletrônico, o comprador pode inserir o código de cupom no campo **código promocional** no carrinho de compras.

Depois que um cupom é adicionado a uma ordem de venda, o mecanismo de preço dispara imediatamente o recálculo da ordem inteira, esteja o cálculo atrasado habilitado ou não.

> [!NOTE]
> No Commerce versão 10.0.30 e anterior, depois que os usuários do call center adicionarem um cupom a uma ordem de venda de call center, eles deverão selecionar **Recalcular** no grupo **Calcular** na guia **Vender** do Painel de Ações para aplicar o desconto associado a esse cupom.

## <a name="coupon-usage-limit"></a>Limite de uso do cupom

Os cupons podem ser configurados para uso limitado. O limite de uso pode ser definido por cliente, por canal ou globalmente. O limite de uso é forçado por código de cupom em um cupom. Por exemplo, um cupom de uso único com dois códigos de cupom pode ser usado duas vezes, uma vez para cada código de cupom.

Os cupons podem ser usados em canais de venda. No entanto, para o call center, os cupons de uso limitado só podem ser aplicados quando a configuração **Habilitar conclusão de ordem** para o canal do call center é habilitada. Se a configuração **Habilitar conclusão de ordem** estiver desabilitada, somente os cupons de uso não limitado poderão ser aplicados.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
