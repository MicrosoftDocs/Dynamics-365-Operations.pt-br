---
title: Preparação do produto
description: Estes tópicos explicam como você pode usar as verificações de prontidão para garantir que os dados mestre necessários sejam preenchidos para um produto antes de usá-los em transações.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8321a0d8516a6c2c085ce9c1236f70af1cca98da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967249"
---
# <a name="product-readiness"></a>Preparação do produto

[!include [banner](../includes/banner.md)]

Você pode usar as verificações de prontidão para garantir que todos os dados mestre tenham sido especificados para um produto antes de usá-los em transações. Quando os cheques de preparação são usados, um usuário ou uma equipe é responsável pela validação de dados predefinidos específicos relacionados a produtos. Se houver uma verificação de preparação aberta para um produto, o produto não poderá ser liberado nem usado em transações.

A caixa de seleção **Ativo** de um produto de engenharia, grade ou versão só estará disponível depois que todos os dados necessários tiverem sido inseridos e verificados, e depois que todas as verificações de preparação tiverem sido processadas. Nesse ponto, o produto, a versão ou a variante podem ser liberados para outras empresas e usados em transações. Você pode criar cheques de preparação para novos produtos, novas grades e novas versões de engenharia.

## <a name="types-of-readiness-checks"></a>Tipos de verificações de preparação

Existem três tipos de verificações de preparação:

- **Verificação do sistema** – O sistema verifica se há um registro válido. Por exemplo, o registro pode ser uma BOM (lista de materiais) ativa.
- **Verificação manual** – Um usuário verifica se o registro é válido. Por exemplo, uma verificação de preparação pode exigir a validação das configurações de ordem padrão. Em alguns casos, por exemplo, quando o produto ainda está sendo criado e, portanto, não é colocado em estoque, nenhuma configuração de ordem padrão é necessária. No entanto, as configurações de ordem padrão podem ser necessárias para outro produto do mesmo tipo, porque o produto pode ser mantido no estoque. O usuário é responsável por saber como decidir corretamente se uma verificação de prontidão é necessária.
- **Lista de verificação** – O usuário responde a uma série de perguntas de uma lista de verificação e o sistema determina se as respostas atendem às expectativas. A lista de verificação pode ter qualquer assunto. Por exemplo, ele pode ser usado para determinar se o material de marketing ou a documentação do produto foi preenchido.

## <a name="how-readiness-checks-are-created-for-a-new-product-variant-or-version"></a>Como as verificações de prontidão são criadas para um novo produto, uma grade ou uma versão

Ao criar um novo produto de **Engenharia**, o sistema determina se uma política de verificação de prontidão foi configurada para a categoria de produto de engenharia. (As políticas de verificação de preparação podem ser aplicadas ao nível de produto liberado, ao nível de grade liberado e ao nível de versão da engenharia.) Se uma diretiva tiver sido configurada, ocorrerão os seguintes eventos:

- As verificações de preparação são criadas para o produto, de acordo com a diretiva aplicável.
- A versão de engenharia está definida como inativa para bloquear o uso do produto. Todas as versões para o produto específico envolvido são definidas como inativas.

Se uma nova **grade** for criada para um produto, o sistema verificará se as verificações de preparação foram configuradas na categoria de produto de engenharia. (As verificações de preparação podem ser aplicadas ao nível de grade liberado e ao nível de versão da engenharia.) Se uma verificação de prontidão tiver sido configurada, ocorrerão os seguintes eventos:

- As verificações de preparação são criadas para o produto.
- A versão de engenharia está definida como inativa para bloquear o uso do produto.

Se uma nova **versão** de engenharia for criada para um produto, o sistema verificará se as verificações de preparação foram configuradas na categoria de produto de engenharia. (As verificações de preparação podem ser aplicadas ao nível de versão da engenharia.) Se uma verificação de prontidão tiver sido configurada, ocorrerão os seguintes eventos:

- As verificações de preparação são criadas para o produto.
- A versão de engenharia está definida como inativa para bloquear o uso do produto.

## <a name="view-readiness-checks"></a>Exibir verificações de preparação

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Exibir verificações de preparação aberta para um produto ou uma versão do produto

Para localizar as verificações de preparação aberta para um produto, abra a página **Detalhes dos produtos liberados**. Em seguida, no Painel de Ação, na guia **Produto**, no grupo **Verificações de prontidão**, selecione **Verificações de prontidão**.

Para localizar as verificações de preparação aberta para uma versão do produto, abra a página **Versões de engenharia** de um produto liberado e escolha uma versão. Em seguida, no Painel de Ação, na guia **Produto**, no grupo **Lista de verificação**, selecione **Verificações de prontidão**.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>Exibir as verificações de preparação aberta atribuídas a você

Para exibir as verificações de preparação de abertura atribuídas a você, siga uma destas etapas.

- Acesse **Gerenciamento de alteração de engenharia \> Comum \> Prontidão do produto \> Minhas verificações de prontidão abertas**.
- Vá para **Gerenciamento de informações de produto \> Espaços de trabalho \> Prontidão de produto para fabricação discreta**.

A configuração que especifica a quem uma verificação de prontidão é atribuída é realizada para a categoria de produto de engenharia. As verificações de preparação podem ser atribuídas a uma pessoa ou a uma equipe. Se uma verificação de prontidão for atribuída a uma equipe, há uma pessoa na equipe que deve processar a verificação de preparação. Para obter mais informações, consulte [Versões de engenharia e categorias de produto de engenharia](engineering-versions-product-category.md).

## <a name="process-open-readiness-checks"></a>Processar verificações de preparação para abertura

### <a name="process-system-and-manual-readiness-checks"></a>Verificações de preparação do sistema de processo e manual

Depois de abrir a página **Verificações de preparação**, você pode exibir o assunto das verificações de preparação manual e do sistema, selecionando **Informações relacionadas** no Painel de ações. Você pode concluir e/ou validar os dados da verificação de preparação. As verificações de prontidão aberta têm um valor de **Status** *Pendente*. Esse status indica que a verificação de preparação ainda deve ser processada. Para processar uma verificação de prontidão, siga uma dessas etapas.

- No Painel de ações, selecione **Verificar/concluir** para revisar e concluir a verificação de preparação. Quando tiver terminado, o campo **Status** será atualizado para *Aprovado*.
- No Painel de ações, selecione **Ignorar** se desejar ignorar uma verificação de prontidão que não é obrigatória. Por exemplo, você configura uma verificação de preparação para cálculos de preço. No entanto, você decide ignorar essa verificação enquanto o produto ainda está na fase de design. Nesse caso, o campo **Status** é atualizado para *Ignorado*.

Dependendo da configuração da diretiva de prontidão, quando o campo **Status** de uma verificação de preparação é atualizado para *Aprovado*, uma etapa extra pode ser necessária para aprovar a verificação de preparação. Nesse caso, selecione **Aprovação** para concluir a verificação de prontidão. Esta etapa de aprovação é sempre obrigatória quando a verificação de preparação é ignorada.

Quando todas as verificações de preparação abertas para um novo produto, grade ou versão tiverem sido processadas e aprovadas conforme necessário, o item se tornará automaticamente ativo e, portanto, pronto para ser usado.

### <a name="process-checklist-readiness-checks"></a>Processar verificações de preparação de lista de verificação

Para abrir uma lista de verificação, abra a página **Verificações de prontidão** e, no painel de ação, selecione **Iniciar lista de verificação**. Depois de concluir a lista de verificação, o sistema valida se a verificação de preparação foi aprovada, com base nas configurações do questionário. Se o cheque for ultrapassado, o campo **Status** será atualizado para *Aprovado*. Se a verificação de preparação não for obrigatória, você poderá ignorá-la. Nesse caso, o campo **Status** é atualizado para *Ignorado*.

Dependendo da configuração da diretiva de prontidão, quando o campo **Status** de uma verificação de preparação é atualizado para *Aprovado*, uma etapa extra pode ser necessária para aprovar a verificação de preparação. Nesse caso, selecione **Aprovação** para concluir a verificação de prontidão. Esta etapa de aprovação é sempre obrigatória quando a verificação de preparação é ignorada.

Quando todas as verificações de preparação abertas para um novo produto, grade ou versão tiverem sido processadas e aprovadas conforme necessário, o item se tornará automaticamente ativo e, portanto, pronto para ser usado.

## <a name="create-and-manage-product-readiness-policies"></a>Criar e gerenciar políticas de preparação do produto

Use as diretivas de preparação do produto para gerenciar as verificações de preparação que se aplicam a um produto. Como uma política de prontidão é atribuída à categoria de engenharia, todas as verificações na política de prontidão se aplicam a todos os produtos de engenharia baseados na categoria de engenharia. Para obter mais informações, consulte [Versões de engenharia e categorias de produto de engenharia](engineering-versions-product-category.md).

Cada política de prontidão contém um conjunto de verificações de preparação. Quando uma política de prontidão é atribuída a uma categoria de produto de engenharia, todos os produtos criados a partir dessa categoria de produto têm as verificações de preparação indicadas na política de prontidão.

Para trabalhar com diretivas de prontidão de produtos, vá para **Gerenciamento de alteração de engenharia \> Configuração \> Políticas de prontidão de produtos**. Siga uma destas etapas.

- Para criar uma nova política, selecione **Novo** no Painel de ações e defina os campos conforme descrito nas subseções a seguir.
- Para editar uma política existente, selecione-o no painel de listas, selecione **Editar** no Painel de ações e defina os campos conforme descrito nas subseções a seguir.
- Para excluir uma diretiva existente, selecione-a no painel de lista, selecione **Editar** no Painel de ações e, na Guia rápida **Geral**, verifique se a opção **Ativo** está definida como *Não*. Em seguida, selecione **Excluir** no Painel de ações.

### <a name="header"></a>Cabeçalho

Defina os campos a seguir no cabeçalho de uma política de prontidão do produto.

| Campo | descrição |
|---|---|
| Organização | Digite um nome para a política. |
| descrição | Insira uma descrição para a política. |

### <a name="general-fasttab"></a>FastTab Geral

Defina os campos a seguir na Guia rápida **Geral** de uma política de prontidão do produto.

| Campo | descrição |
|---|---|
| Tipo de Produto | Selecione se a diretiva se aplica a produtos do tipo *Item* ou *Serviço*. Não é possível alterar essa configuração após salvar o registro. |
| Com atividade | Use esta opção para ajudar a manter as políticas de prontidão. Defina como *Sim* para todas as diretivas de prontidão que você usa. Defina como *Não* para marcar uma política de prontidão como inativa quando ela não for usada. Observe que não é possível desativar uma diretiva de preparação atribuída a uma categoria de produto de engenharia, e você pode excluir somente as diretivas de liberação inativas. |

### <a name="readiness-control-fasttab"></a>Guia rápida de controle de prontidão

Para cada tipo de verificação de preparação que você deseja incluir na diretiva, adicione uma linha na Guia rápida **Controle de prontidão**. Use os botões a seguir na barra de ferramentas da Guia rápida para adicionar e remover linhas conforme necessário:

- **Adicionar verificação** – Adiciona uma verificação de prontidão padrão à política. Quando você seleciona este botão, a caixa de diálogo **Adicionar verificação** é exibida. Nela, você pode selecionar a partir de uma lista de cheques disponíveis.
- **Adicionar questionário existente** – Adicione uma linha em branco à grade. Em seguida, você pode atribuir um questionário existente definindo os campos na tabela a seguir.
- **Copiar** – Adicione uma cópia da linha selecionada à grade.
- **Excluir** – Exclui a linha selecionada da grade.

Para cada linha adicionada, defina os campos a seguir.

| Campo | descrição |
| --- | --- |
| Área do processo | Selecione a área à qual a verificação está relacionada. |
| Tipo | Selecione se o cheque for uma verificação do sistema, uma verificação manual ou uma lista de verificação (questionário). |
| Organização | Se o cheque for uma lista de verificação, insira um nome. Para verificações manuais e de sistema, este campo é definido automaticamente. |
| descrição | Se o cheque for uma lista de verificação, insira uma descrição. Para verificações manuais e de sistema, este campo é definido automaticamente e a descrição explica o foco do cheque. |
| Aplicar cheques em | Selecione se a linha deve gerar cheques de preparação em resposta a um novo produto liberado, uma grade liberada ou uma versão liberada. |
| Executar em | Selecione se as verificações de preparação que a linha gera aplicam a todas as empresas ou a uma única empresa. |
| Empresa | Se você definir o campo **Executar em** como *Uma única empresa*, selecione a empresa. |
| Tipo do proprietário | Selecione se as verificações de preparação que a linha gera devem ser atribuídas a uma pessoa ou a uma equipe. |
| Proprietário | Selecione se as verificações de preparação que a linha gera devem ser atribuídas a uma pessoa ou a uma equipe. |
| Questionário | Selecione o questionário que deve ser usado para a lista de verificação. A lista de verificação é uma lista de verificação local na empresa na qual a verificação de preparação está concluída. O sistema deve ser capaz de avaliar se a lista de verificação foi respondida corretamente. Portanto, a lista de verificação deve ser configurada de forma que uma avaliação seja feita com base nas respostas corretas. Para obter mais informações sobre como criar questionários, consulte [Usando questionários](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/using-questionnaires) e os tópicos relacionados. |
| Aprovação automática | Os registros de verificação de prontidão incluem uma caixa de seleção **Aprovado** que indica o status da aprovação. Marque a caixa de seleção **Aprovação automática** para verificações que devem ser definidas como aprovados imediatamente após o usuário atribuído concluí-los. Desmarque esta caixa de seleção para exigir aprovação explícita como uma etapa extra. |
| Obrigatório | Marque esta caixa de seleção para os cheques que devem ser concluídos pelo usuário atribuído. As verificações obrigatórias não podem ser ignoradas. |
