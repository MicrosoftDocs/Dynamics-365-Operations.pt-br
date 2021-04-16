---
title: Passo a passo do recurso Gerenciamento de alterações de engenharia
description: Este tópico fornece uma orientação completa que mostra como trabalhar com o gerenciamento de alterações de engenharia.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 91b19598075871dcfaed3ad9978aa8fe8181aa6f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836653"
---
# <a name="engineering-change-management-feature-walkthrough"></a>Passo a passo do recurso Gerenciamento de alterações de engenharia

[!include [banner](../includes/banner.md)]

Este tópico fornece uma orientação completa que mostra como trabalhar com o gerenciamento de alterações de engenharia. Ele passa por cada um dos cenários mais importantes:

- Configuração de recurso básico
- Como uma empresa de engenharia cria um novo produto de engenharia
- Como uma empresa de engenharia libera um produto de engenharia para uma empresa local
- Como uma empresa local pode revisar e aceitar um produto que foi liberado por uma empresa de engenharia
- Como uma empresa local pode usar um produto de engenharia em transações padrão
- Como adicionar um produto de engenharia a uma ordem de venda
- Como solicitar alterações em um produto de engenharia criando uma solicitação de alteração de engenharia
- Como agendar e implementar alterações solicitadas criando uma ordem de alteração de engenharia
- Como liberar um produto que foi alterado

Todos os exercícios neste tópico usam os dados de exemplo padrão fornecidos para o Microsoft Dynamics 365 Supply Chain Management. Além disso, cada exercício se baseia no exercício anterior. Portanto, é recomendável trabalharmos com exercícios em ordem, do início ao fim, especialmente se você nunca tiver usado o recurso de gerenciamento de alterações de engenharia. Dessa forma, você obterá uma compreensão completa do recurso.

## <a name="set-up-for-the-sample-scenario"></a>Configurar o cenário de exemplo

Para seguir o cenário de exemplo fornecido neste tópico, primeiro você deve preparar o recurso disponibilizando os dados de demonstração e adicionando alguns registros personalizados.

Antes de tentar executar qualquer um dos exercícios no restante deste tópico, siga as instruções em todas as subseções a seguir. Essas subseções também apresentam várias páginas de configurações importantes que serão usadas quando você configurar o gerenciamento de alterações de engenharia para sua própria organização.

### <a name="make-standard-demo-data-available"></a>Disponibilizar dados de demonstração padrão

Trabalhe em um sistema no qual os [dados de demonstração padrão estejam instalados](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Os dados de demonstração padrão adicionam dados a várias entidades legais de demonstração (empresas e organizações). Ao trabalhar nos exercícios, você usará o seletor da empresa no lado direito da barra de navegação para alternar entre uma empresa (*DEMF*) que é configurada como uma *organização de engenharia* e outra empresa (*USMF*) que é configurada como uma *organização operacional*.

### <a name="set-up-an-engineering-organization"></a>Configurar uma organização de engenharia

Uma organização de engenharia possui os dados de engenharia e é responsável pelo design e pelas alterações em produtos. Para configurar organizações de engenharia, siga estas etapas.

1. Acesse **Gerenciamento de alterações de engenharia &gt; Configuração &gt; Organizações de engenharia**.
1. Selecione **Novo** para adicionar uma linha à grade e defina os seguintes valores para ela:

    - **Organização de engenharia:** *DEMF*
    - **Nome da organização:** *Contoso Entertainment System Germany*

    ![Adicionar uma organização de engenharia](media/engineering-org.png "Adicionar uma organização de engenharia")

### <a name="set-up-the-version-product-dimension-group"></a>Configurar o grupo de dimensões do produto da versão

1. Acesse **Gerenciamento de informações do produto &gt; Configuração &gt; Grupos de dimensões e variantes &gt; Grupos de dimensões do produto**.
1. Selecione **Novo** para criar um grupo de dimensões do produto.
1. Defina o campo **Nome** como *Versão*.
1. Selecione **Salvar** para salvar os novos valores de dimensão e de carga na FastTab **Dimensões do produto**.
1. Na FastTab **Dimensões do produto**, defina a **Versão** como uma dimensão do produto ativa.

    ![Adicionar um grupo de dimensões do produto](media/product-dimension-groups.png "Adicionar um grupo de dimensões do produto")

### <a name="set-up-product-lifecycle-states"></a>Configurar estados de ciclo de vida do produto

Conforme um produto de engenharia passa pelo ciclo de vida, é importante que você consiga controlar quais transações são permitidas para cada estado do ciclo de vida. Para configurar os estados de ciclo de vida do produto, siga estas etapas.

1. Vá para **Gerenciamento de alteração de engenharia &gt; Configuração &gt; Estado de ciclo de vida do produto**.
1. Selecione **Novo** para adicionar um estado de ciclo de vida e defina os seguintes valores para ele:

    - **Estado:** *Operacional*
    - **Descrição:** *Operacional*

1. Selecione **Salvar** para salvar os novos valores de estado de ciclo de vida e de carga na FastTab **Processos comerciais habilitados**.
1. Na FastTab **Processos comerciais habilitados**, selecione os processos comerciais que devem estar disponíveis. Neste exemplo, deixe o campo **Política** definido como *Habilitado* para todos os processos comerciais.

    ![Habilitar processos comerciais para um estado de ciclo de vida](media/product-lifecycle-states-1.png "Habilitar processos comerciais para um estado de ciclo de vida")

1. Selecione **Novo** para adicionar outro estado de ciclo de vida e defina os seguintes valores para ele:

    - **Estado:** *Protótipo*
    - **Descrição:** *Protótipo*

1. Selecione **Salvar** para salvar os novos valores de estado de ciclo de vida e de carga na FastTab **Processos comerciais habilitados**.
1. Na FastTab **Processos comerciais habilitados**, selecione os processos comerciais que devem estar disponíveis. Neste exemplo, defina o campo **Política** como *Habilitado com aviso* para todos os processos comerciais.

    ![Habilitar (com avisos) processos comerciais para um estado de ciclo de vida](media/product-lifecycle-states-2.png "Habilitar (com avisos) processos comerciais para um estado de ciclo de vida")

### <a name="set-up-a-version-number-rule"></a>Configurar uma regra de número de versão

1. Vá para **Gerenciamento de alteração de engenharia &gt; Configuração &gt; Regra de número de versão do produto**.
1. Selecione **Novo** para adicionar uma regra e defina os seguintes valores para ela:

    - **Nome:** *Automático*
    - **Regra de número:** *Automático*
    - **Formato:** *V-\#\#*

    ![Adicionar uma regra de número de versão do produto](media/version-number-rule.png "Adicionar uma regra de número de versão do produto")

### <a name="set-up-a-product-release-policy"></a>Configurar uma política de liberação do produto

1. Vá para **Gerenciamento de alteração de engenharia &gt; Configuração &gt; Políticas de liberação do produto**.
1. Selecione **Novo** para adicionar uma política de liberação e defina os seguintes valores para ela:

    - **Nome:** *Componentes*
    - **Descrição:** *Componentes*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Tipo de produto:** *Item*
    - **Aplicar modelos:** *Sempre*
    - **Ativo:** *Sim*

1. Na FastTab **Todos os produtos**, selecione **Adicionar** para adicionar uma linha e defina os seguintes valores para ela:

    - **Empresa:** *DEMF*
    - **Produto liberado de modelo:** *D0006*

1. Selecione **Adicionar** para adicionar outra linha e defina os seguintes valores para ela:

    - **ID de contas da empresa:** *USMF*
    - **Produto liberado de modelo:** *D0006*
    - **Receber BOM:** marque esta caixa de seleção.
    - **Copiar aprovação de BOM:** marque esta caixa de seleção.
    - **Copiar ativação de BOM:** marque esta caixa de seleção.
    - **Receber roteiro:** marque esta caixa de seleção.
    - **Copiar aprovação de roteiro:** marque esta caixa de seleção.
    - **Copiar ativação de roteiro:** marque esta caixa de seleção.

    ![Adicionar uma política de liberação do produto](media/product-release-policy.png "Adicionar uma política de liberação do produto")

### <a name="set-up-an-engineering-product-category"></a>Configurar uma categoria de produto de engenharia 

As categorias de produtos de engenharia fornecem a base para a criação de produtos de engenharia (ou seja, produtos com versão e controlados por meio do gerenciamento de alterações de engenharia). Para configurar categorias de produtos de engenharia, siga estas etapas.

1. Acesse **Gerenciamento de alterações de engenharia &gt; Detalhes de categorias de produtos de engenharia**.
1. Selecione **Novo** para criar uma categoria.
1. Na FastTab **Detalhes**, defina os seguintes valores:

    - **Nome:** *Componentes*
    - **Organização de engenharia:** *DEMF*
    - **Tipo de produto:** *Item*
    - **Rastrear versão em transações:** *Sim*
    - **Grupo de dimensões do produto:** *Versão*
    - **Estado do ciclo de vida do produto na criação:** *Operacional*
    - **Regra de número de versão:** *Automático*
    - **Aplicar efetividade:** *Não*
    - **Usar nomenclatura da regra de número:** *Não*
    - **Usar nomenclatura da regra de nome:** *Não*
    - **Usar nomenclatura da regra de descrição:** *Não*

1. Na FastTab **Política de liberação**, defina o campo **Política de liberação do produto** como *Componentes*.
1. Selecione **Salvar**.

    ![Adicionar uma categoria de produto de engenharia](media/product-category-details.png "Adicionar uma categoria de produto de engenharia")

### <a name="set-up-product-acceptance-conditions"></a>Configurar condições de aceitação do produto

1. Use o seletor da empresa no lado direito da barra de navegação para alternar para entidade legal *USMF* (empresa).
1. Acesse **Gerenciamento de alterações de engenharia &gt; Configuração &gt; Parâmetros de gerenciamento de alterações de engenharia**.
1. Na guia **Controle de liberação**, na seção **Aceitação do produto**, defina o campo **Aceitação do produto** como *Manual*.

    ![Configurar condições de aceitação do produto](media/engineering-change-management-parameters.png "Configurar condições de aceitação do produto")

## <a name="create-a-new-engineering-product"></a>Criar um novo produto de engenharia

Um produto de engenharia é um produto com versão e controlado pelo gerenciamento de alterações de engenharia. Em outras palavras, você pode controlar as alterações durante a vida útil e as informações de alteração serão salvas usando ordens de alteração de engenharia. Para criar produtos de engenharia, siga estas etapas.

1. Verifique se você está na entidade legal da organização de engenharia (*DEMF*, por exemplo). Use o seletor da empresa no lado direito da barra de navegação, conforme necessário.
1. Abra a página **Produtos liberados**, seguindo uma destas etapas:

    - Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**.
    - Vá para **Gerenciamento de alteração de engenharia &gt; Comum &gt; Produtos liberados**.

1. No Painel de Ações, na guia **Produto**, no grupo **Novo**, selecione **Produto de engenharia**.
1. Na caixa de diálogo **Novo produto**, defina os seguintes valores:

    - **Categoria de Produto de Engenharia:** *Componentes*
    - **Número do produto:** *Z0001*
    - **Nome do produto:** *Conjunto de palestrantes*

    ![Adicionar um produto de engenharia](media/new-product-dialog.png "Adicionar um produto de engenharia")

    Observe que o campo **Versão** é automaticamente definido usando a regra número de versão do produto configurada anteriormente.

1. Selecione **OK** para criar o produto e fechar a caixa de diálogo.
1. A página de detalhes do novo produto será aberta. Observe que os valores já estão preenchidos para alguns campos, como **Grupo de dimensões de armazenamento**, **Grupo de dimensões de rastreamento** e/ou **Grupo de modelos de item**. Esses campos foram automaticamente definidos porque o produto está sendo liberado na entidade legal *DEMF* e usa a política de liberação de produtos de *Componentes*, que está associada à categoria de produto de engenharia de *Componentes*. Como você utilizou anteriormente o item *D0006* como um modelo para configurar uma linha para a entidade legal *DEMF*, os valores que foram preenchidos foram obtidos do item *D0006*.

    ![Detalhes do produto liberado](media/product-details.png "Detalhes do produto liberado")

1. No Painel de Ações, na guia **Engenheiro**, no grupo **Gerenciamento de alterações de engenharia**, selecione **Versões de engenharia** para exibir as versões do produto.

    ![Versões de engenharia](media/engineering-versions-list.png "Versões de engenharia")

1. Na página **Versões de engenharia**, observe que existe apenas uma versão do produto e ela está ativa.
1. Selecione a versão para exibir detalhes.

    ![Detalhes da versão de engenharia](media/engineering-version-details.png "Detalhes da versão de engenharia")

1. Na página **Versão da engenharia**, na FastTab **Lista de materiais**, selecione **Criar BOM**.
1. Na caixa de diálogo **Criar BOM**, defina os seguintes valores:

    - **Número de BOM:** Z0001
    - **Nome**: conjunto de palestrantes
    - **Local:** 1

    ![Criando uma BOM](media/create-bom.png "Criando uma BOM")

1. Selecione **OK** para adicionar a BOM e feche a caixa de diálogo.
1. Na FastTab **Lista de materiais**, selecione **Lista de materiais**.
1. Na página **Lista de materiais**, na FastTab **Linhas da lista de materiais**, adicione três linhas, uma para cada número de item *D0001*, *D0003* e *D0006*.

    ![Adicionar linhas de BOM](media/bom.png "Adicionar linhas de BOM")

1. Selecione **Salvar**.
1. Feche a página.
1. Na página **Versão da engenharia**, na FastTab **Lista de materiais**, selecione **Aprovar**.
1. Na caixa de diálogo exibida, selecione **OK**.

    ![Aprovar a BOM](media/approve-dialog.png "Aprovar a BOM")

1. Na página **Versão da engenharia**, na FastTab **Lista de materiais**, selecione **Ativar**.
1. Note que as caixas de seleção **Ativa** e **Aprovada** estão selecionadas para a BOM.

    ![Ativar e aprovar BOM](media/approved-bom.png "Ativar e aprovar BOM")

1. Feche a página.

## <a name="release-an-engineering-product-to-a-local-company"></a><a name="release"></a>Liberar um produto de engenharia para uma empresa local

O produto foi criado pelo departamento de engenharia. Neste exemplo, o produto é um protótipo que a engenharia criou para um cliente. Como o cliente é um cliente da entidade legal *USMF*, o produto deve ser liberado para essa entidade legal.

1. Mantenha a entidade legal definida como *DEMF*. (Use o seletor da empresa no lado direito da barra de navegação, conforme necessário.)
1. Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**.
1. Selecione o produto *Z0001*.
1. No Painel de Ações, na guia **Produto**, no grupo **Manter**, selecione **Liberar a estrutura de produtos** para abrir o assistente para **Liberar produtos**.
1. Na página **Selecionar produtos de engenharia a serem liberados**, marque a caixa de seleção **Selecionar** para o produto *Z0001*.

    ![Selecionar os produtos de engenharia a serem liberados](media/select-eng-product-to-release.png "Selecionar os produtos de engenharia a serem liberados")

1. Selecione **Detalhes da versão**.
1. A página **Detalhes da versão do produto** é exibida, na qual você pode revisar os detalhes do produto que será liberado e sua estrutura de produtos. Note que a opção **Enviar BOM** está definida como *Sim*. Portanto, o produto *Z0001* e todos os itens filhos da BOM serão liberados.

    Você pode selecionar qualquer item filho no painel esquerdo para revisar os detalhes. Se algum item filho tiver uma BOM, você também poderá optar por liberar a BOM desse item filho.

    ![Analisar os detalhes da versão do produto](media/product-release-details.png "Analisar os detalhes da versão do produto")

1. Feche a página para retornar ao assistente para **Liberar produtos**.
1. Selecione **Avançar** para abrir a página **Selecionar produtos a serem liberados**. Se você tiver selecionado produtos padrão (sem engenharia), eles aparecerão nesta página. Observe que, quando você libera um produto padrão selecionando **Liberar a estrutura de produtos**, a BOM e o roteiro também são liberados.

    ![Selecionar os produtos padrão a serem liberados](media/select-std-product-to-release.png "Selecionar os produtos padrão a serem liberados")

1. Selecione **Avançar** para abrir a página **Selecionar variantes de produtos a serem liberados**. Neste exemplo, não há variantes.
1. Selecione **Avançar** para abrir a página **Selecionar empresas**.
1. Selecione as empresas para as quais o produto deve ser liberado. Para este exemplo, marque a caixa de seleção para **USMF**.

    ![Selecionar as empresas para liberação](media/select-release-companies.png "Selecionar as empresas para liberação")

1. Selecione **Avançar** para abrir a página **Confirmar seleção**.
1. Selecione **Concluir**.

## <a name="review-and-accept-the-product-before-you-release-it-in-the-local-company"></a><a name="accept"></a>Revisar e aceitar o produto antes de liberá-lo na empresa local

O departamento de engenharia liberou as informações para as empresas locais nas quais o produto será usado. Para este exemplo, a empresa local é *USMF*.

Como você definiu o campo **Aceitação do produto** como *Manual* na página **Parâmetros de gerenciamento de alterações da engenharia** para a empresa *USMF*, os produtos devem ser aceitos manualmente antes de serem liberados para essa empresa. Em outras palavras, os produtos devem ser revisados e aceitos antes de serem lançados.

Para revisar o produto e liberá-lo na empresa *USMF*, siga estas etapas.

1. Defina a entidade legal definida como *USMF*. (Use o seletor da empresa no lado direito da barra de navegação.)
1. Acesse **Gerenciamento de alterações de engenharia &gt; Comum &gt; Liberações de produtos &gt; Liberações de produtos em aberto**.

    A página **Liberações de produtos em aberto** mostra o produto *Z0001*, que tem um status *Aceitação pendente*.

    ![Abrir liberações de produtos](media/open-product-releases.png "Abrir liberações de produtos")

1. Selecione o valor na coluna **Número do produto** para abrir a página **Detalhes da liberação do produto**. Observe os seguintes detalhes:

    - A FastTab **Geral** mostra informações sobre a liberação do produto, como a empresa de liberação (*DEMF*, neste exemplo), o site de liberação (*1*) e o site de recebimento (*1*). Como você não especificou um site de recebimento no assistente para **Liberar produtos**, o valor do site de liberação é copiado para o site de recebimento.
    - A FastTab **Detalhes da liberação** mostra informações sobre o produto e a versão liberada. Aqui, você pode modificar as configurações, como as datas de efetividade.
    - A FastTab **Roteiro** mostra o roteiro do produto. No entanto, para esse exemplo, não foi possível liberar roteiros.

    ![Detalhes da liberação do produto](media/product-release-details-2.png "Detalhes da liberação do produto")

1. Ao concluir a revisão das informações, você estará pronto para aceitar o produto e, dessa forma, liberá-lo na empresa *USMF*. No Painel de Ações, selecione **Ações &gt; Aceitar**.
1. O produto agora está liberado na empresa *USMF*. Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**. Você deve ver o item *Z0001*.

## <a name="use-the-product-in-transactions-in-the-local-company"></a>Usar o produto em transações na empresa local

O gerente de dados mestres da empresa *USMF* deseja garantir que o produto esteja em estado de *Protótipo* para garantir que os usuários sejam avisados se eles o adicionarem acidentalmente aos processos executados.

1. Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**.
1. Selecione o produto *Z0001* para abrir a página de detalhes. (Você pode usar o filtro para localizar o produto.)
1. No Painel de Ações, na guia **Engenheiro**, no grupo **Gerenciamento de alterações de engenharia**, selecione **Versões de engenharia**.
1. Na página **Versões de engenharia**, selecione número da versão *V-01* para abrir a página de detalhes.
1. No Painel de Ações, na guia **Produto**, no grupo **Estado de ciclo de vida**, selecione **Alterar estado de ciclo de vida**.
1. Na caixa de diálogo suspensa **Alterar estado de ciclo de vida**, defina o campo **Estado** como *Protótipo* e selecione **OK**.

    ![Alterar o estado de ciclo de vida](media/change-lifecycle-state.png "Alterar o estado de ciclo de vida")

## <a name="add-the-engineering-product-to-a-sales-order"></a>Adicionar o produto de engenharia a uma ordem de venda

O produto pode ser vendido agora para um cliente. Para adicionar o produto a uma ordem de venda, siga estas etapas:.

1. Vá para **Vendas e marketing &gt; Ordens de venda &gt; Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda**, defina o campo **Conta do cliente** como *US-0002* e selecione **OK**.
1. A nova ordem de venda é aberta. Na FastTab **Linhas da ordem de venda**, adicione uma linha e defina o campo **Número do item** como *Z000*.
1. No Painel de ações, selecione **Salvar**.

    Você receberá uma mensagem de aviso informando que o item tem status de *Protótipo*. No entanto, como a mensagem é apenas um aviso, a ordem de venda ainda foi criada.

    ![Ordem de venda para um produto de engenharia](media/sales-order-eng-product.png "Ordem de venda para um produto de engenharia")

## <a name="request-changes-in-the-engineering-product"></a>Solicitar alterações no produto de engenharia

O produto foi enviado a um cliente, mas o cliente não ficou totalmente satisfeito e fornece comentários que incluem sugestões para melhoria. Enquanto o cliente fala com um auxiliar de vendas por telefone, o auxiliar de vendas pode solicitar as alterações que o cliente descreve.

1. Vá para **Vendas e marketing &gt; Ordens de venda &gt; Todas as ordens de venda**.
1. Localize e abra a ordem de venda criada no exercício anterior.
1. Na FastTab **Linhas da ordem de venda**, selecione **Gerenciamento de alterações de engenharia &gt; Nova solicitação de alteração de engenharia**.

    ![Criar uma solicitação de alteração de engenharia a partir de uma ordem de venda](media/sales-order-eng-change-request.png "Criar uma solicitação de alteração de engenharia a partir de uma ordem de venda")

1. Preencha a solicitação de alteração da engenharia, com base nos comentários do cliente. Para este exemplo, defina os seguintes valores:

    - **Solicitação de alteração:** *555*
    - **Título:** *alteração do cliente Z0001*
    - **Prioridade:** *baixa*
    - **Categoria:** definir alteração
    - **Gravidade:** *média*

1. Na FastTab **Informações**, selecione **Novo &gt; Nota** para adicionar uma nota à grade.
1. No campo **Descrição** da nova nota, indique que o item *D0003* deve ser excluído da BOM. Se for necessário adicionar mais informações à nota, você poderá inserir texto no campo **Notas**.

    ![Solicitação de alteração de engenharia](media/eng-change-request.png "Solicitação de alteração de engenharia")

1. No Painel de ações, selecione **Salvar**.
1. Observe que o item foi adicionado automaticamente na FastTab **Produtos** e que a origem da solicitação de alteração da engenharia (a ordem de venda) foi adicionada na FastTab **Fonte**.

## <a name="make-changes-to-the-product-by-using-an-engineering-change-order"></a>Fazer alterações no produto usando uma ordem de alteração de engenharia

O auxiliar de vendas sabe que o produto é importante e foi criado especialmente para o cliente. Portanto, o auxiliar de vendas chama um engenheiro na empresa *DEMF* para notificá-los sobre a solicitação de alteração. Dessa forma, o engenheiro pode acelerar o processo.

O engenheiro agora revisa a solicitação do cliente e cria uma ordem de alteração para o produto.

1. Como o engenheiro trabalha na empresa *DEMF*, defina a entidade legal como *DEMF*. (Use o seletor da empresa no lado direito da barra de navegação.)
1. Acesse **Gerenciamento de alterações de engenharia &gt; Comum &gt; Solicitações de alterações de engenharia**.
1. Abra a solicitação de alteração: *555*.
1. Revise as informações e aprove a alteração. No Painel de Ações, na guia **Solicitação de alteração**, no grupo **Alterar status**, selecione **Aprovar**.
1. Acesse **Gerenciamento de alterações de engenharia &gt; Comum &gt; Ordens de alterações de engenharia**.
1. No Painel de Ações, selecione **Novo** para criar uma ordem de alteração e defina os seguintes valores:

    - **Ordem de alteração**: *555*
    - **Título:** *alteração do cliente Z0001*
    - **Categoria:** *alteração de cliente*
    - **Prioridade:** *baixa*
    - **Gravidade:** *média*

1. Na FastTab **Produtos afetados**, selecione **Novo &gt; Adicionar produto existente** para adicionar uma linha à grade e, depois, defina os seguintes valores para ela:

    - **Produto:** *Z0001*
    - **Impacto:** *nova versão*

    ![Criar uma ordem de alteração de engenharia](media/eng-change-order.png "Criar uma ordem de alteração de engenharia")

1. Observe que, como você definiu o campo **Impacto** como *Nova versão*, o campo **Nova versão** na guia **Detalhes** da FastTab **Detalhes do produto** mostra qual será o novo número de versão (*V-02* neste exemplo).

    ![Detalhes do produto para uma ordem de alteração de engenharia](media/eng-change-order-product-details.png "Detalhes do produto para uma ordem de alteração de engenharia")

1. No Painel de ações, selecione **Salvar**.
1. Na FastTab **Detalhes do produto**, na guia **Lista de materiais**, selecione **Linhas** para abrir a BOM para a versão *V-01* do produto *Z0001*.

    ![Linhas da BOM de produto de engenharia](media/eng-product-bom-lines.png "Linhas da BOM de produto de engenharia")

1. Selecione a linha do número do item *D0003* e, no Painel de Ações, selecione **Excluir**. O valor do campo **Alterar tipo** para esta linha é alterado para *Excluído*.
1. No Painel de ações, selecione **Salvar**.

    ![Linhas modificadas da BOM de produto de engenharia](media/eng-product-bom-lines-modified.png "Linhas modificadas da BOM de produto de engenharia")

1. Feche a página **Linha da BOM** para retornar à página **Ordem de alteração de engenharia**.
1. Na FastTab **Detalhes do produto**, na guia **Lista de materiais**, observe que o valor do campo **Alterar tipo** da BOM *Z0001* agora é *Alterado*.

    ![Ordem de alteração de engenharia que inclui uma BOM alterada](media/eng-change-order-changed-bom.png "Ordem de alteração de engenharia que inclui uma BOM alterada")

    A ordem deve ser aprovada antes do processamento das alterações. Quando as alterações são processadas, os produtos são atualizados com as alterações incluídas na ordem de alteração da engenharia. Neste exemplo, a pessoa que cria a ordem de alteração de engenharia foi especificada como aprovador.

1. No Painel de Ações, na guia **Ordem de alteração**, no grupo **Alterar status**, selecione **Aprovar**.
1. Selecione **Processo** para atualizar as informações do produto.

## <a name="release-the-changed-product"></a>Liberar o produto alterado

O produto pode ser liberado novamente para a empresa *USMF* e enviado ao cliente. Para liberar o produto diretamente da ordem de alteração da engenharia, siga estas etapas.

1. Abra a ordem de alteração de engenharia criada no exercício anterior, caso ainda não esteja aberta.
1. No Painel de Ações, na guia **Ordem de alteração**, no grupo **Liberações do produto**, selecione **Pesquisar**.
1. Os resultados da pesquisa mostram para que empresas os produtos afetados foram liberados. Feche os resultados da pesquisa.
1. No Painel de Ações, na guia **Ordem de alteração**, no grupo **Liberações do produto**, selecione **Exibir** para abrir a caixa de diálogo **Liberações**, na qual você pode exibir os resultados da pesquisa anterior.
1. Selecione cada empresa para a qual deseja liberar produtos.
1. Selecione **OK** para fechar a caixa de diálogo **Liberações** e retornar à ordem de alteração.
1. No Painel de Ações, na guia **Ordem de alteração**, no grupo **Liberações do produto**, selecione **Processar** para liberar os produtos afetados para as empresas selecionadas. Como alternativa, selecione **Liberar a estrutura de produtos** para iniciar o processo de liberação.

## <a name="complete-the-change-order"></a>Concluir a ordem de alteração

Para marcar a ordem de alteração como concluída, o que indica que não há outras ações restantes, selecione **Concluir** no Painel de Ações.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
