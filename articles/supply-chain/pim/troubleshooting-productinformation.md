---
title: Solucionar problemas de informações do produto
description: Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com informações do produto.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a9db8e0081a0d47ec8d74680fe99a0934b99bb5c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223353"
---
# <a name="troubleshoot-product-information"></a>Solucionar problemas de informações do produto

Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com informações do produto.

## <a name="i-cant-delete-a-released-product"></a>Não consigo excluir um produto liberado.

### <a name="issue-description"></a>Descrição do problema

É possível excluir um produto liberado e todas as suas variantes somente se o produto liberado não tiver nenhuma transação relacionada.

### <a name="issue-resolution"></a>Resolução do problema

Siga as etapas a seguir para excluir um produto liberado ou produto mestre.

1. Feche todas as transações em aberto para os itens.
1. Reduza o estoque a 0 (zero).
1. Realize o fechamento do estoque.
1. Exclua todas as variantes do produto para o produto mestre que você deseja excluir.

## <a name="can-i-change-the-item-number-of-a-released-product"></a>Posso alterar o número do item de um produto liberado?

Na maioria dos casos, não é possível editar os números dos itens para produtos liberados, porque essa alteração fará com que os dados sejam corrompidos. Você pode editar o número do item apenas se precisar reparar dados corrompidos por uma renomeação anterior da chave primária desse produto liberado, conforme mencionado na lista de [recursos removidos ou preteridos do Finance and Operations 10.0.0 com atualização da plataforma 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).

Se você quiser editar os números dos itens de produtos liberados, [vote nessa ideia no portal de ideias](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a>O princípio de liberação padrão do produto não está sendo inserido na linha da lista de materiais.

### <a name="issue-description"></a>Descrição do problema

Quando você adiciona um item a uma linha de lista de materiais (BOM), o sistema não usa as informações do princípio de liberação padrão configuradas para o item. Em outras palavras, o princípio de liberação do item não aparece na página **Linha BOM**.

### <a name="issue-resolution"></a>Resolução do problema

Se você especificar um princípio de liberação em uma linha BOM, ele se aplicará a essa linha BOM. Contudo, se o princípio de liberação estiver em branco ou se não for definido em uma linha BOM, o princípio de liberação definido no item ainda se aplicará a essa linha BOM, embora não seja mostrado nela.

A lógica padrão para outros recursos no Microsoft Dynamics 365 Supply Chain Management geralmente não funciona dessa maneira. No entanto, o comportamento atual não pode ser alterado. Caso contrário, algumas personalizações existentes que dependem dele podem ser interrompidas.

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a>O sistema me permite salvar códigos de barras duplicados para itens diferentes ou para o mesmo item que possui dimensões diferentes.

Atualmente, o sistema não impõe códigos de barras exclusivos e a adição dessa restrição seria uma alteração significativa. Na verdade, a Microsoft tem evidências de que algumas instalações existentes do cliente seriam interrompidas por essa mudança. Entretanto, consideraremos uma mudança de design mais ampla para habilitar esse recurso no futuro.

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a>Recebo a seguinte mensagem de erro quando edito modelos de registro de item: "O local do depósito não pode ser criado porque o item não está em estoque. Para itens de estoque, a opção de produto em estoque no grupo de modelo de item associado deve ser selecionada."

### <a name="issue-description"></a>Descrição do problema

Esse problema ocorre se você seguir essas etapas para tentar criar um modelo para um item que não está em estoque.

1. Abra um produto liberado que não está em estoque.
1. No Painel de ações, na guia **Opções**, selecione **Informações sobre registro**.
1. Na caixa de diálogo **Informações sobre registro**, selecione **Modelo de contas da empresa**.

Nesse caso, você receberá a seguinte mensagem de erro:

> O local do depósito não pode ser criado porque o item não está em estoque. Para itens de estoque, a opção de produto em estoque no grupo de modelo de item associado deve ser selecionada.

### <a name="issue-resolution"></a>Resolução do problema

O processo de criação de modelos de produto requer lógica extra específica do produto. Portanto, você não pode usar o botão **Modelo de contas da empresa** genérico para essa finalidade. Em vez disso, siga estas etapas:

1. Abra um produto liberado.
1. No Painel de ações, na guia **Produto**, no grupo **Novo**, selecione **Modelo \> Criar modelo compartilhado**.

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a>O texto de ajuda padrão adicionado aos atributos do produto não é inserido em um produto liberado.

Uma descrição e um texto de ajuda adicionados aos atributos do produto não são visíveis ou inseridos por padrão nos produtos liberados. Esse comportamento é por design.

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a>A quantidade padrão inserida difere quando é registrada de uma BOM e quando é registrada de uma versão da BOM.

### <a name="issue-description"></a>Descrição do problema

Por padrão, quando você adiciona um item a uma BOM, a quantidade é definida como 1 em vez da quantidade definida no campo **Quantidade mínima para ordem** na página **Configurações de ordem padrão** para um produto selecionado. No entanto, quando você adiciona um item de uma versão da BOM e o item e a variante são selecionados, a quantidade inserida por padrão leva em consideração a quantidade mínima definida nas configurações padrão da ordem para as dimensões específicas.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é esperado. Contudo, o fato de que a lógica difere na BOM e na versão da BOM é um problema conhecido. Esse comportamento, porém, não será alterado, porque uma mudança pode afetar muitos cenários de clientes diferentes.

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a>Nos detalhes do produto liberado, não posso alterar as imagens anexadas que foram carregadas da entidade de dados de anexos do documento do produto.

### <a name="issue-description"></a>Descrição do problema

Esse problema pode ocorrer quando você anexa uma imagem a um item usando a entidade de dados *Anexos do documento do produto*. Nesse caso, a imagem de item é mostrada para o item. Contudo, se você selecionar **Alterar imagem**, nada será mostrado na lista de imagens carregadas. Além disso, nenhum anexo é mostrado para o item.

### <a name="issue-resolution"></a>Resolução do problema

A entidade *EcoResProductDocumentAttachmentEntity* (*Anexos do documento do produto*) importa anexos do documento para *produtos*, mas não para *produtos liberados*. (Os produtos liberados também são conhecidos como *items*.) Para exibir os anexos de um item na página **Detalhes do produto liberado**, você deve usar a entidade *EcoResReleasedProductDocumentAttachmentEntity* (*Anexos de documentos de produtos liberados*) em vez disso.

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a>O conector do Microsoft Flow mostra a seguinte mensagem de erro: "Atualização não permitida para o campo 'ProductNumber'."

### <a name="issue-description"></a>Descrição do problema

Esse problema ocorre se você tentar atualizar o campo **Número do produto** usando a entidade V2 *Produtos liberados* e o Microsoft Flow.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é esperado. A capacidade de editar o número do produto para um produto liberado foi removida no Dynamics 365 Finance and Operations 10.0.0 com a atualização de plataforma 24 para ajudar a evitar a corrupção de dados. Em casos excepcionais, quando você deve reparar dados corrompidos causados por uma renomeação anterior da chave primária de um produto liberado, você pode pedir ao Suporte da Microsoft para remover temporariamente essa restrição.

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a>Não consigo criar uma variante de produto liberado em outra entidade legal.

### <a name="issue-description"></a>Descrição do problema

Se você tentar liberar um produto mestre sem variantes e depois criar as variantes em cada entidade legal (empresa) conforme necessário, não poderá liberar as variantes usando sugestões de variantes. Você também não poderá criar as variantes manualmente.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é por design. As relações de um produto mestre e as dimensões que o mestre pode assumir são mantidas em um nível compartilhado. Portanto, você não pode criar as dimensões disponíveis para um produto mestre compartilhado na entidade legal específica onde essas dimensões são liberadas e, depois, replicar o processo em cada entidade legal onde as dimensões são necessárias. Em vez disso, você deve alterar seu processo de liberação para se adaptar ao processo criado.

Aqui está o processo de liberação de produtos.

1. Crie o produto mestre compartilhado e as dimensões que podem ser liberadas para as entidades legais.
1. Libere os produtos para as entidades legais usando sugestões de variantes ou adicionando manualmente as combinações que devem ser liberadas.

Como alternativa, você pode criar diretamente o produto liberado.

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a>Quando libero uma variante em outra empresa, recebo a seguinte mensagem de erro: "A variante do produto com as dimensões especificadas já foi criada."

### <a name="issue-description"></a>Descrição do problema

Se uma variante de produto já tiver sido liberada em uma empresa A e você tentar liberá-la na empresa B usando o botão **Novo** na página **Grades de produtos liberadas**, você receberá o seguinte erro mensagem:

> A grade de produto com dimensões especificadas já foi criada.

### <a name="issue-resolution"></a>Resolução do problema

O botão **Novo** na página **Grades de produtos liberadas** cria a variante e a libera no contexto da empresa. Se a variante já foi criada, você não pode usar o botão **Novo** para liberá-la em outra empresa.

Para corrigir o problema, abra a página **Produto mestre** e selecione **Liberar produto** para liberar a variante existente na empresa desejada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]