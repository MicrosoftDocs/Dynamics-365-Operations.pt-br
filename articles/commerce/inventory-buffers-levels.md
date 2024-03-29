---
title: Configurar buffers de estoque e níveis de estoque
description: Este artigo explica como configurar buffers de estoque e níveis de estoque que determinam mensagens de disponibilidade de estoque em sites do Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 5f882debd09a7076a52606f7ca3aca97d9ec8afe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269183"
---
# <a name="configure-inventory-buffers-and-inventory-levels"></a>Configurar buffers de estoque e níveis de estoque

[!include [banner](includes/banner.md)]

Este artigo explica como configurar buffers de estoque e níveis de estoque que determinam as mensagens sobre disponibilidade de estoque em sites do Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce headquarters contém dados de estoque e vários canais, como aplicativos de ponto de venda (PDV), lojas de comércio eletrônico e outros aplicativos integrados personalizados que recebem e empurram o estoque de forma assíncrona. Portanto, os valores de estoque disponíveis obtidos por meio da página de estoque disponível no Commerce headquarters, por meio da interface de usuário do PDV (IU) e por APIs de disponibilidade de estoque de comércio eletrônico nem sempre são 100% precisos em tempo real.

Em vez de mostrar valores de estoque reais em lojas de comércio eletrônico, muitos varejistas preferem apenas mostrar as mensagens sobre o status de disponibilidade do estoque (por exemplo, "Disponível" ou "Esgotado") para informar aos clientes se um item está disponível para compra ou potencialmente esgotado. Para essa abordagem, os buffers de estoque e os níveis de estoque que determinam as mensagens de disponibilidade de estoque devem ser disponibilizados e configurados.

## <a name="prerequisite-turn-on-the-inventory-buffers-and-inventory-levels-feature"></a>Pré-requisito: Ativar o recurso de buffers de estoque e níveis de estoque

O recurso para buffers de estoque e níveis de estoque é controlado pelo gerenciamento de recursos no Commerce headquarters. Para ativar o recurso, siga estas etapas.

1. Acesse **Administrador do sistema** \> **Espaços de trabalho** \> **Gerenciamento de recursos**.
1. Procure o recurso **Habilitar buffers de estoque e níveis de estoque**, selecione sua linha e, em seguida, selecione **Habilitar agora**.

Depois que o recurso tiver sido ativado, você poderá encontrar os níveis de estoque em **Varejo e Comércio \> Gerenciamento de estoque**.

## <a name="create-and-configure-an-inventory-level-profile"></a>Criar e configurar um perfil de nível de estoque

Um *perfil de nível de estoque* determina se um determinado status de quantidade do produto é considerado em estoque, esgotado ou algum outro status personalizado. Você pode criar e configurar vários perfis de nível de estoque por entidade legal. Cada perfil consiste em um conjunto de níveis de estoque e cada nível é definido por um *intervalo*, um *código* e um *rótulo*.

- **Intervalo** – cada intervalo é definido por uma *quantidade inicial* e uma *quantidade final*. Um valor de quantidade ocorre em um intervalo, se for maior do que a quantidade inicial desse intervalo e não mais do que a quantidade final.
- **Código** – um código é uma abreviação interna que representa o nível. Os clientes que integram diretamente as APIs de estoque podem usar códigos para criar lógicas adicionais para um nível de estoque específico. Por exemplo, eles poderão desativar o recurso de compra para um produto quando seu código de nível de estoque for **OOS** ("esgotado").
- **Etiqueta** – uma etiqueta é uma mensagem significativa voltada para o cliente que transmite um nível de estoque para os clientes em um site de comércio eletrônico.

### <a name="create-an-inventory-level-profile"></a>Criar um perfil de nível de estoque

Para criar um perfil de nível de estoque, siga estas etapas.

1. Acesse **Retail e Commerce** \> **Gerenciamento de estoque** \> **Níveis de estoque**.
1. No Painel de Ações, selecione **Novo** e insira os valores nos campos **ID do Perfil** e **Descrição**.
1. Na Guia Rápida **Intervalos**, selecione **Adicionar** para adicionar um novo nível e insira os valores nas colunas **Quantidade inicial**, **Quantidade final**, **Código** e **Etiqueta** desse nível. Repita essa etapa para adicionar mais níveis. Conforme necessário, você pode editar os valores na grade de dados ou pode selecionar **Excluir** para remover um nível.
1. No Painel de ações, selecione **Salvar**.

Quando um novo perfil é criado, dois níveis de estoque são inicializados automaticamente:

- **OOS** – o nível "esgotado", em que o limite inferior do intervalo é o infinito negativo. A quantidade inicial e o código não podem ser editados para esse nível.
- **DISP** - o nível "disponível", em que o limite superior do intervalo é o infinito. A quantidade final e o código não podem ser editados para esse nível.

> [!NOTE]
> Não pode haver lacunas ou sobreposição entre intervalos na definição de perfil.

Você pode usar o botão **Traduções** no Painel de Ações para configurar cadeias de caracteres localizadas para a mensagem de etiqueta. Em seguida, você deve executar o trabalho de agendamento de distribuição **1110** (**Configuração global**) para sincronizar as cadeias de caracteres localizadas com os canais.

### <a name="configure-an-inventory-level-profile"></a>Configurar um perfil de nível de estoque

Você pode configurar um perfil de nível de estoque no nível de categoria de produto ou de produto individual. Quando um perfil de nível de estoque é configurado para um produto, o nível de estoque é determinado com base nos intervalos definidos no perfil vinculado. Caso contrário, o nível de estoque "disponível" ou "esgotado" será determinado com base no fato de o produto ter uma quantidade disponível positiva.

Para configurar um perfil de nível de estoque para uma categoria, siga estas etapas.

1. Acesse **Retail e Commerce** \> **Produtos e categorias** \> **Hierarquia de produtos do Commerce**.
1. Selecione a categoria para a qual configurar um perfil de nível de estoque.
1. Na Guia Rápida **Propriedades de produtos de venda**, selecione uma entidade legal.
1. Na seção **Estoque do Commerce**, no campo **Perfil de nível de estoque**, selecione um dos perfis de nível de estoque predefinidos.

Você pode usar o botão **Atualizar produtos** no Painel de Ações para propagar o valor do perfil de nível de categoria para os produtos subjacentes da categoria. Para obter mais informações, consulte [Gerenciar categorias de produtos e produtos](category-management-product-creation.md).

Para configurar um perfil de nível de estoque para um produto liberado, siga estas etapas.

1. Acesse **Retail e Commerce** \> **Produtos e categorias** \> **Produtos liberados por categoria**.
1. Selecione um produto e abra sua página de detalhes.
1. Na Guia Rápida **Vender**, na seção **Estoque do Commerce**, no campo **Perfil de nível de estoque**, selecione um dos perfis de nível de estoque predefinidos.

Quando um novo produto é criado, o campo **Perfil de nível de estoque**, como muitos outros atributos de nível de produto, será definido como o valor configurado para a categoria à qual o produto está associado.

> [!NOTE]
> O perfil do nível de estoque é um atributo específico da entidade legal. Para a mesma categoria ou produto, o valor do perfil de nível de estoque pode variar em entidades legais.

Para sincronizar as configurações de perfis de nível de estoque com os canais, siga estas etapas.

1. Acesse **Retail e Commerce** \> **TI de Varejo e Comércio** \> **Agenda de distribuição**.
1. Execute a agenda de distribuição **1040** (**Produto**).

## <a name="configure-an-inventory-buffer"></a>Configurar um buffer de estoque

O *buffer de estoque* é um valor definido pelo usuário que subtrai a quantidade adicional de um item da quantidade original para calcular a quantidade estimada. Essa quantidade estimada fornece aos varejistas um buffer seguro para que não haja a venda de um produto acima do estoque disponível real. Você pode configurar o buffer do estoque no nível de categoria de produto ou de produto individual. Se nenhum buffer de estoque for especificado, o valor padrão **0** (zero) será usado.

Para configurar o buffer de estoque para uma categoria, siga estas etapas.

1. Acesse **Retail e Commerce** \> **Produtos e categorias** \> **Hierarquia de produtos do Commerce**.
1. Selecione a categoria para a qual o buffer de estoque será configurado.
1. Na Guia Rápida **Propriedades de produtos de venda**, selecione uma entidade legal.
1. Na seção **Estoque do Commerce**, no campo **Buffer de estoque**, insira um valor positivo.

Você pode usar o botão **Atualizar produtos** no Painel de Ações para propagar o valor do buffer no nível de categoria para os produtos subjacentes da categoria. Para obter mais informações, consulte [Gerenciar categorias de produtos e produtos](category-management-product-creation.md).

Para configurar o buffer de estoque para um produto liberado, siga estas etapas.

1. Acesse **Retail e Commerce** \> **Produtos e categorias** \> **Produtos liberados por categoria**.
1. Selecione um produto e abra sua página de detalhes.
1. Na Guia Rápida **Venda**, na seção **Estoque do Commerce**, no campo **Buffer de estoque**, insira um valor positivo.

Quando um novo produto é criado, o campo **Buffer de estoque**, como muitos outros atributos de nível de produto, será definido como o valor configurado para a categoria à qual o produto está associado.

> [!NOTE]
> Se os perfis de nível de estoque e de buffer de estoque estiverem configurados para um produto, a quantidade prevista do produto (ou seja, a quantidade original menos o valor do buffer) será usada para o cálculo de intervalo para determinar o nível de estoque.

Para sincronizar as configurações de buffers de estoque com os canais, siga estas etapas.

1. Acesse **Retail e Commerce** \> **TI de Varejo e Comércio** \> **Agenda de distribuição**.
1. Execute a agenda de distribuição **1040** (**Produto**).

## <a name="use-inventory-buffers-and-inventory-levels-in-e-commerce-scenario"></a>Usar buffers de estoque e níveis de estoque no cenário de comércio eletrônico

O construtor de sites do Commerce usa os recursos do nível de estoque e de buffer de estoque no Commerce headquarters para determinar a disponibilidade de estoque em sites de comércio eletrônico. Para obter mais informações, consulte [aplicar configurações de estoque](inventory-settings.md).

Como alternativa, se você integrar com uma solução de comércio eletrônico de terceiros, poderá usar as APIs **GetEstimatedAvailability** e **GetEstimatedProductWarehouseAvailability** para mostrar a disponibilidade do estoque para um produto no cenário de comércio eletrônico. Para obter mais informações sobre essas APIs, consulte [Calcular disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md).

A introdução de buffers de estoque e níveis de estoque permite que essas APIs retornem códigos de nível de estoque e mensagens de etiquetas que são determinadas com base nos valores de total disponível e físicos disponíveis. As APIs podem ser configuradas para determinar se a quantidade de estoque é devolvida com a mensagem e se a quantidade disponível é reduzida pelo valor do buffer de estoque.

Para configurar a resposta das APIs de disponibilidade do produto, siga estas etapas.

1. Acesse **Retail e Commerce** \> **Configuração do headquarters** \> **Parâmetros** \> **Parâmetros do Commerce**.
1. Na seção **Estoque de loja**, na guia **Estoque**, no campo **APIs de disponibilidade do produto para comércio eletrônico**, selecione um valor.
1. Para aplicar as configurações aos canais, execute o trabalho de agendamento de distribuição **1110** (**Configuração global**).

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciar produtos e categorias de produtos](category-management-product-creation.md)

[Aplicar configurações de estoque](inventory-settings.md)

[Calcular disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
