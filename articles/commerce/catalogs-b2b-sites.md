---
title: Criar catálogos do Commerce para sites B2B
description: Este artigo descreve como criar catálogos do Commerce para sites B2B (entre empresas) do Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 7d87b6c64a6038c4518eeec178f9e139ef6f5ae2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848980"
---
# <a name="create-commerce-catalogs-for-b2b-sites"></a>Criar catálogos do Commerce para sites B2B

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo descreve como criar catálogos de produtos do Commerce para sites B2B (entre empresas) do Microsoft Dynamics 365 Commerce. Para obter respostas a perguntas frequentes sobre catálogos do Commerce para sites B2B, consulte [Perguntas frequentes sobre Catálogos do Commerce para B2B](catalogs-b2b-sites-FAQ.md).

> [!NOTE]
> Este artigo se aplica ao Dynamics 365 Commerce versão 10.0.27 e a versões posteriores.

Você pode usar catálogos do Commerce para identificar os produtos que deseja oferecer em suas lojas online B2B. Quando você cria um catálogo, identifica as lojas online em que os produtos são oferecidos, adiciona os produtos desejados e melhora as ofertas de produtos adicionando detalhes das mercadorias. Você pode criar vários catálogos para as lojas online B2B.

Os catálogos de produtos do Commerce permitem definir as seguintes informações:

- **Hierarquia de navegação específica do catálogo** – as organizações podem criar uma estrutura de categoria distinta para o catálogo específico.
- **Metadados de atributos específicos do catálogo** – os atributos contêm detalhes sobre um produto. Atribuindo atributos a uma categoria da hierarquia de navegação, você pode definir valores para esses atributos no nível de produtos atribuídos a essa categoria. As organizações podem concluir estas tarefas:

    - Defina valores de atributo específicos do catálogo.
    - Controle a visibilidade dos atributos no nível do catálogo.
    - Selecione os refinadores específicos de um catálogo individual.

- **Canais** – as organizações podem associar mais de um canal online B2B a um catálogo. No momento, o suporte de ponta a ponta para catálogos está disponível apenas para lojas online B2B.
- **Hierarquias de clientes** – para um determinado canal B2B, as organizações podem disponibilizar um catálogo específico para parceiros B2B selecionados associando hierarquias de clientes a esse catálogo.
- **Grupos de preços** – você pode configurar preços e promoções específicos para um determinado catálogo. Esse recurso é o principal motivo para definir um catálogo para um canal B2B. Os grupos de preços dos catálogos permitem que as organizações disponibilizem produtos para as organizações B2B pretendidas e apliquem seus preços e descontos preferenciais. Os clientes B2B que fazem pedidos de um catálogo configurado podem se beneficiar de preços e promoções especiais após entrarem em um site B2B do Commerce. Para configurar preços específicos do catálogo, selecione **Grupos de preços** na guia **Catálogos** para vincular um ou mais grupos de preços ao catálogo. Todos os contratos comerciais, diários de ajuste de preço e descontos avançados que forem vinculados ao mesmo grupo de preços serão aplicados quando os clientes fizerem pedidos usando este catálogo. (Os descontos avançados incluem os descontos de limite, quantidade e compra combinada.) Para obter mais informações sobre grupos de preços, consulte [Grupos de preços](price-management.md#price-groups).

> [!NOTE]
> Este recurso está disponível a partir da versão 10.0.27 do Dynamics 365 Commerce. Para definir configurações específicas do catálogo, como hierarquia de navegação e hierarquia de clientes, no Commerce headquarters, abra o espaço de trabalho **Gerenciamento de recursos** (**Administração do sistema \> Espaços de trabalho \> Gerenciamento de recursos**), habilite o recurso **Habilitar o uso de vários catálogos em canais de varejo** e execute o trabalho **1110 CDX**.

## <a name="catalog-process-flow"></a>Fluxo do processo do catálogo

O processo de criação e processamento de um catálogo tem quatro etapas gerais. Cada etapa será explicada em detalhes na próxima seção.

1. **[Configuração](#configure-the-catalog)**

    - Associe a hierarquia de navegação.
    - Especifique as datas de efetivação e vencimento, se forem aplicáveis.
    - Adicione e categorize produtos.
    - Associe grupos de preços.
    - Associe uma hierarquia de clientes específica às organizações B2B. 
    - Associe o grupo de atributos de dimensão padrão para refinadores, como tamanho, estilo e cor.
    - Defina metadados de atributo.

1. **[Validação](#validate-the-catalog)** – nesta etapa, você executa regras de validação que impõem um comportamento específico. Veja alguns exemplos:

    - Verifique se não há produtos não categorizados.
    - Certifique-se de que todos os itens classificados em cada canal estejam associados a um catálogo.

1. **[Aprovação](#approve-the-catalog)**
1. **[Publicando](#publish-the-catalog)**

## <a name="set-up-the-catalog"></a>Definir o catálogo

Use as informações desta seção para configurar o catálogo.

### <a name="configure-the-catalog"></a>Configurar o catálogo

No Commerce headquarters, acesse **Varejo e comércio \> Catálogos e sortimentos \> Todos os catálogos** para configurar o catálogo.

Ao criar um novo catálogo, é necessário primeiro associá-lo a um ou mais canais. Somente os itens vinculados ao canal selecionado [sortimentos](/dynamics365/unified-operations/retail/assortments) podem ser usados quando o catálogo é criado. Para associar o catálogo a um ou mais canais, selecione **Adicionar** na guia rápida **Canais do Commerce** da página **Configuração do catálogo**.

#### <a name="associate-the-navigation-hierarchy"></a>Associar a hierarquia de navegação

Para adicionar produtos a um catálogo, é necessário selecionar uma hierarquia de navegação. A hierarquia de navegação é compatível com a estrutura da categoria do catálogo. É necessário selecionar uma das hierarquias de navegação associadas aos canais selecionados na guia rápida **Canais do Commerce** da página **Configuração de catálogo**. Para associar uma hierarquia de navegação padrão a cada um dos canais, acesse **Varejo e comércio \> Configuração de canal \> Categorias de canais e atributos de produtos**.

#### <a name="specify-time-effective-and-expiration-dates"></a>Especificar as datas de efetivação e vencimento

Para especificar datas de efetivação e vencimento para um catálogo, selecione o nó superior da hierarquia do catálogo para retornar à exibição principal do cabeçalho do catálogo. Em seguida, na guia rápida **Geral**, configure as datas de efetivação e vencimento conforme necessário.

#### <a name="add-and-categorize-products"></a>Adicionar e categorizar produtos

Para configurar os produtos a serem adicionados ao catálogo, no Commerce headquarters, acesse **Varejo e comércio \> Catálogos e sortimentos \> Todos os catálogos**. Em seguida, na guia **Catálogos**, selecione **Adicionar produtos**.

Como alternativa, selecione um nó na hierarquia de navegação. Em seguida, será possível adicionar produtos diretamente a uma categoria no catálogo.

#### <a name="associate-price-groups"></a>Associar grupos de preços

Para configurar preços específicos do catálogo, é necessário vincular um ou mais grupos de preços ao catálogo. Para associar grupos de preços a um catálogo, no Commerce headquarters, acesse **Varejo e comércio \> Catálogos e sortimentos \> Todos os catálogos**. Em seguida, na guia **Catálogos**, em **Preço**, selecione **Grupos de preços**. Todos os contratos comerciais, diários de ajuste de preço e descontos avançados (limite, quantidade e descontos de compra combinada) que forem vinculados ao mesmo grupo de preços serão aplicados quando os clientes solicitarem o catálogo.

Para obter mais informações sobre grupos de preços, consulte [Grupos de preços](price-management.md#price-groups).

> [!NOTE]
> Não é possível criar um novo grupo de preços na página **Todos os catálogos**. É necessário criá-lo na página **Todos os grupos de preços**. Em seguida, é necessário associá-lo ao catálogo na página **Todos os catálogos**.

#### <a name="associate-a-customer-hierarchy"></a>Associar uma hierarquia de clientes

Para associar hierarquias de clientes, no Commerce headquarters, acesse **Varejo e comércio \> Catálogos e sortimentos \> Todos os catálogos**. Em seguida, na guia **Catálogos**, em **Hierarquia de clientes**, selecione **Atribuir hierarquias** para vincular uma ou mais hierarquias de clientes ao catálogo.

> [!NOTE]
> Não é possível criar uma nova hierarquia de clientes na página **Todos os catálogos**. É necessário criá-la na página **Hierarquias de clientes**. Em seguida, é necessário associá-lo ao catálogo na página **Todos os catálogos**.

#### <a name="associate-default-dimension-attribute-group-for-refiners-such-as-size-style-and-color"></a>Associar o grupo de atributos de dimensão padrão para refinadores, como tamanho, estilo e cor

Para associar um grupo de atributos de dimensão padrão para refinadores, como tamanho, estilo e cor, no Commerce headquarters, acesse **Varejo e comércio \> Catálogos e sortimentos \> Todos os catálogos**. Em seguida, na guia **Catálogos**, em **Atributos**, selecione **Grupos de atributos**.

#### <a name="set-attribute-metadata"></a>Definir metadados de atributo

Para configurar metadados de atributo, no Commerce headquarters, acesse **Varejo e comércio \> Catálogos e sortimentos \> Todos os catálogos**. Em seguida, na guia **Catálogos**, em **Atributos**, selecione **Definir metadados de atributo**. Para selecionar os atributos que devem ser visualizados e refinados, selecione uma categoria na hierarquia de navegação específica do catálogo associado e, em **Atributos do produto do catálogo**, selecione um atributo. Em seguida, selecione **Mostrar atributo no canal**. Por padrão, todos os atributos visíveis também podem ser pesquisados. Opcionalmente, para tornar os atributos refináveis, selecione **Pode ser refinado**.

### <a name="validate-the-catalog"></a>Validar o catálogo

Antes que um novo catálogo esteja disponível para uso, ele deve ser validado e publicado.

Para validar um catálogo, siga estas etapas.

1. Na guia **Catálogos** da página **Todos os catálogos**, em **Validar**, selecione **Validar catálogo** para executar uma validação. Esta etapa é obrigatória. Ela validará se a configuração necessária for precisa.
1. Selecione **Exibir resultados** para exibir os detalhes da validação. Se forem encontrados erros, será necessário corrigir os dados e, em seguida, executar a validação novamente até que ela seja aprovada.

### <a name="approve-the-catalog"></a>Aprovar o catálogo

Depois que um catálogo é validado, ele deve ser aprovado.

Para iniciar o fluxo de trabalho de aprovação do catálogo, siga estas etapas.

1. No painel de ações da página **Todos os catálogos**, selecione **Fluxo de trabalho \> Enviar**.
1. Acesse **Varejo e comércio \> Configuração do headquarters \> Fluxos de trabalho do Commerce** para configurar as etapas e os usuários autorizados para o fluxo de trabalho. O fluxo de trabalho definirá as etapas necessárias para colocar o catálogo em um status **Aprovado**.

### <a name="publish-the-catalog"></a>Publicar o catálogo

Depois que um catálogo estiver no status **Aprovado**, você poderá publicá-lo selecionando **Publicar** no menu **Catálogos**. Depois do catálogo estiver em um estado **Publicado** , ele poderá ser usado na entrada de ordem do call center e nos processo de envio do catálogo. Você pode publicar um catálogo manualmente ou usando um processo em lote. A data de efetivação definida para o catálogo determina quando os produtos são disponibilizados na loja online. A data de vencimento definida determina quando os produtos são removidos da loja online.

> [!NOTE]
> Você pode publicar um catálogo com produtos que tenham avisos. No entanto, esses produtos não aparecerão na loja online.

## <a name="additional-resources"></a>Recursos adicionais

[Impacto da extensibilidade de catálogos do Commerce para personalizações B2B](catalogs-b2b-sites-dev.md)

[Perguntas frequentes sobre Catálogos do Commerce para B2B](catalogs-b2b-sites-FAQ.md)
