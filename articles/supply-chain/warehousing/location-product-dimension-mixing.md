---
title: Combinação de dimensões do produto de localização
description: Este tópico fornece informações sobre a combinação de dimensões do produto de localização. Essa funcionalidade do perfil de localização ajuda a melhorar o gerenciamento de localização quando grades de produtos ou produtos que têm dimensões são usados, como na indústria da moda. Ela permite decidir se configurações, cores, estilos e tamanhos podem ser combinados para um perfil de localização específico ou se apenas uma dessas dimensões ou uma combinação delas podem ser colocadas no mesmo local.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 73519f3fe79d3d7d917d3044255f735640b8ccfd
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422506"
---
# <a name="location-product-dimension-mixing"></a>Combinação de dimensões do produto de localização

[!include [banner](../includes/banner.md)]

A combinação de dimensões do produto de localização é uma funcionalidade do perfil de localização que ajuda a melhorar o gerenciamento de localização quando grades de produtos ou produtos que têm dimensões são usados, como na indústria da moda. Ela permite decidir se configurações, cores, estilos e tamanhos podem ser combinados para um perfil de localização específico ou se apenas uma dessas dimensões ou uma combinação delas podem ser colocadas no mesmo local.

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a>Ativar o recurso Combinação de dimensões do produto de localização

Para que você possa usar a combinação de dimensões do produto de localização, o recurso deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Combinação de dimensões do produto de localização*

## <a name="setup"></a>Instalação

Cada local no depósito precisa ter um perfil de localização associado a ele que descreva suas propriedades. Portanto, todos os locais que usam o mesmo perfil de localização poderão permitir a combinação de dimensões do produto após sua configuração.

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a>Configurar perfis de localização para permitir a combinação de dimensões do produto

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.
1. Na lista de perfis de localização, selecione **MASSA**.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Geral**, defina a opção **Habilitar a combinação específica de dimensões do produto de localização** como *Sim*.

    > [!NOTE]
    > Você só poderá definir essa opção como *Sim* se a opção **Permitir itens mistos** estiver definida como *Não*.

1. Na FastTab **Combinação de dimensões do produto permitida**, defina a opção **Tamanho** como *Sim*. No cenário descrito neste tópico, a combinação pode ser feita somente para produtos com dimensões de **Tamanho** diferentes. No entanto, outras opções também estão disponíveis.
1. Selecione **Salvar**.

### <a name="create-a-new-product-master-and-product-variants"></a>Criar um novo produto mestre e grades de produtos

1. Vá para **Gerenciamento de informações sobre produtos \> Produtos \> Produtos mestre**.
1. No Painel de Ação, selecione **Novo** para criar um produto mestre.
1. Na caixa de diálogo **Novo produto**, defina os seguintes valores:

    - **Tipo de produto:** *Item*
    - **Subtipo de produto:** *Produto mestre*
    - **Número do produto:** *B0001*
    - **Nome do produto:** *Tamanho B0001*
    - **Grupo de dimensões do produto:** *Tamanho*
    - **Tecnologia de configuração:** *Grade predefinida*

1. Selecione **OK**.
1. Na página **Detalhes do produto**, na FastTab **Geral**, defina os seguintes valores:

    - **Gerar grades automaticamente:** *Sim*
    - **Grupo de tamanhos:** *CASUALDHIR*

1. Para exibir as grades predefinidas, no Painel de Ação, selecione **Grades de produtos**.

    A página **Grades de produtos** é exibida e mostra uma lista de grades da configuração do grupo de tamanhos.

### <a name="release-products-to-the-usmf-company"></a>Liberar produtos para a empresa USMF

1. No Painel de Ação, selecione **Liberar produtos**.
1. Na página **Selecionar produtos para liberação**, confirme que o produto de número *B0001* está na lista e, em seguida, selecione **Avançar**.
1. Selecione **Avançar** para confirmar as grades de produtos a serem liberadas.
1. Na página **Selecionar empresas para as quais os produtos serão liberados**, selecione *USMF* e, em seguida, selecione **Avançar** para confirmar a seleção.
1. Na página **Confirmar seleção**, selecione **Concluir** para concluir a liberação.

    Você receberá uma mensagem "Operação concluída".

### <a name="update-a-released-product-in-the-usmf-company"></a>Atualizar um produto liberado na empresa USMF

1. Entre na empresa **USMF**.
1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados** para concluir a criação do produto liberado.
1. Localize e selecione o item de número *B0001* para abrir a página **Detalhes do produto liberado**.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Geral**, verifique se o campo **Grupo de modelo do item** está definido como *PEPS*.
1. No Painel de Ação, na guia **Produto**, no grupo **Configuração**, selecione **Grupos de dimensões**.
1. Defina os seguintes valores:

    - **Grupo de dimensões de armazenamento:** *Ware*
    - **Grupo de dimensões de rastreamento:** *Nenhum*

1. Selecione **OK**.
1. No Painel de Ação, na guia **Produto**, no grupo **Configuração**, selecione **Hierarquia de reservas**.
1. Defina o campo **Hierarquia de reservas** como *Padrão* e, em seguida, selecione **OK**.
1. Na FastTab **Geral**, na seção **Administração**, observe que suas seleções foram atualizadas.
1. Na FastTab **Compra**, no campo **Preço**, insira *10*.
1. Na FastTab **Gerenciar custos**, no campo **Grupo de itens**, insira *Áudio*.
1. Na FastTab **Compra**, no campo **Preço**, insira *10*.
1. Na FastTab **Depósito**, no campo **ID do grupo de sequências de unidade**, insira *ea*.
1. Selecione **Salvar**.

### <a name="create-a-location-directive"></a>Criar uma diretiva de localização

1. Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No painel esquerdo, no campo **Tipo de ordem de serviço**, selecione *Ordens de compra*.
1. Na lista, selecione a diretiva de localização chamada *24 PO Direct*.
1. Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Número de sequência:** *1*

        A nova linha deve estar na frente da linha previamente existente. Para fazer a alteração, use os botões **Mover para cima** e **Mover para baixo** na barra de ferramentas ou altere o valor do **Número de sequência** da linha existente para *2*.

    - **Nome:** *Colocar no Perfil de localização MASSA*
    - **Uso de localização fixa:** *Localizações fixas e não fixas*
    - **Permitir estoque negativo:** *Desmarcar esta caixa de seleção (=Não)*
    - **Lote habilitado:** *Desmarcar esta caixa de seleção (=Não)*
    - **Estratégia:** *Nenhuma*

1. Com a nova linha ainda selecionada, selecione **Editar consulta** acima da grade.
1. Na caixa de diálogo de consulta, na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Tabela:** *Localizações*
    - **Tabela derivada:** *Localizações*
    - **Campo:** *ID de perfil da localização*
    - **Critérios:** *MASSA*

1. Selecione **OK**.
1. Na página **Diretivas de localização**, no Painel de Ação, selecione **Salvar**.

> [!NOTE]
> No campo **Estratégia** da FastTab **Ações de Diretiva de Localização**, se você usar a estratégia de localização *Consolidar*, a configuração da FastTab **Combinação de dimensões do produto permitida** nos **Perfis de localização** será substituída, e os itens serão colocados no mesmo local, mesmo que esse comportamento não seja permitido pela configuração.

### <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ação, selecione **Novo** para criar um item de menu a ser usado para classificação.
1. No cabeçalho, defina os seguintes valores:

    - **Nome do item de menu:** *Recebimento da linha da OC*
    - **Título:** *Recebimento da linha da OC*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Não*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Processo de criação de trabalho:** *Recebimento e armazenamento da linha da ordem de compra*
    - **Gerar placa de licença:** *Sim*

1. Selecione **Salvar**.

### <a name="configure-the-mobile-device-menu"></a>Configurar o menu do dispositivo móvel

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. Na lista de menus, selecione **Entrada**.
1. No Painel de Ações, selecione **Editar**.
1. Na lista **Menus e Itens de Menu Disponíveis**, localize e selecione o item de menu **Recebimento da linha da OC**.
1. Selecione o botão de seta para a direita a fim de mover o item de menu **Recebimento da linha da OC** para a lista **Estrutura de Menu**. Dessa forma, você adiciona o novo item de menu ao menu selecionado.
1. Selecione **Salvar**.

## <a name="scenario"></a>Cenário

Este cenário de demonstração mostra como duas grades de produtos diferentes podem ser colocadas no mesmo local quando o perfil de localização não permite itens mistos, mas o recurso *Combinação de dimensões do produto de localização* está habilitado. Nesse caso, você usará a grade **Tamanho** como o critério.

Antes de começar, verifique se há locais vazios no depósito *24* que usem o perfil de localização *MASSA*.

### <a name="create-a-purchase-order"></a>Criar uma ordem de compra

Você criará uma ordem de compra com três linhas: duas linhas para o mesmo número de produto, mas diferentes grades de **Tamanho**, e uma terceira linha para um produto diferente que não tem grades.

1. Vá para **Contas a pagar \> Ordens de compra \> Todas as ordens de compra**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:

    - **Conta do fornecedor:** *1001*
    - **Depósito:** *24*

1. Selecione **OK**.
1. A ordem de compra é criada e uma nova linha é adicionada à FastTab **Linhas da ordem de compra**. Anote o número da ordem de compra.
1. Na nova linha, defina os valores a seguir:

    - **Número de item:** *B0001*
    - **Tamanho** *G*
    - **Quantidade:** *2*

1. Selecione **Adicionar linha** acima da grade para adicionar uma segunda linha da ordem de compra e defina os seguintes valores:

    - **Número de item:** *B0001*
    - **Tamanho** *GG*
    - **Quantidade:** *2*

1. Selecione **Adicionar linha** para adicionar uma terceira linha da ordem de compra e defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *1*

1.Selecione **Salvar**.

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a>Receber linhas da ordem de compra no aplicativo de depósito

1. Entre no aplicativo de depósito como um usuário habilitado para o depósito *24*.
1. Selecione o menu **Entrada**.
1. Selecione **Recebimento da Linha da OC**.
1. Selecione o campo **PONUM** e insira o número da ordem de compra.
1. Confirme a entrada selecionando o botão de confirmação ( ✔ ) na parte inferior da página.
1. Insira o número da linha da ordem de compra que está sendo recebida. Selecione o campo **LINENUM** e use o teclado numérico para inserir *1*.
1. Confirme a entrada.
1. Insira a quantidade a ser recebida. Selecione o botão de sinal de adição (**+**) duas vezes para aumentar o valor no campo **Qtd.** para *2*.
1. Registre a entrada selecionando o botão ( ✔ ) na parte inferior da página e, em seguida, confirme a entrada selecionando o botão ( ✔ ) novamente.
1. Veja as informações na página **Ordens de compra: colocar**. Essa página mostra o trabalho criado para o armazenamento (Trabalho 1).

    O local onde o item recebido será armazenado, a placa de licença​, o item, o tamanho e a quantidade da tarefa **Recebimento da Linha da OC** que você acabou de concluir são exibidos.

1. Confirme o trabalho de armazenamento.
1. Repita as etapas 4 a 11 para a linha 2 da ordem de compra. No entanto, na etapa 8, especifique uma quantidade de *1*.

    Um novo trabalho de armazenamento (Trabalho 2) é criado para o mesmo local que o Trabalho 1.

1. Repita as etapas 4 a 11 novamente para a linha 2 da ordem de compra. Na etapa 8, especifique a quantidade restante de *1*.

    Um novo trabalho de armazenamento (Trabalho 3) é criado para o mesmo local que o Trabalho 1 e o Trabalho 2. Esse comportamento ocorre porque a estratégia da diretiva de localização *Consolidar* é usada, e a FastTab **Combinação de dimensões do produto permitida** na configuração de **Perfis de localização** *Massa* permite que a grade **Tamanho** seja combinada em um local.

1. Repita as etapas 4 a 11 para a linha 3 da ordem de compra. Na etapa 8, especifique uma quantidade de *1* para o item de número *A0001*.

    Um novo trabalho de armazenamento (Trabalho 4) é criado para um local diferente do local usado para as linhas 1 e 2 da ordem de compra. Esse comportamento ocorre porque o perfil de localização não permite produtos mistos, mas permite dimensões mistas do mesmo produto mestre.

1. Selecione o botão Menu na parte superior da página (às vezes chamado de hambúrguer ou botão de hambúrguer) e, em seguida, selecione **Cancelar** para sair do **Recebimento da Linha da OC**.

> [!TIP]
> Você pode repetir esse cenário, mas desta vez, defina **Tamanho** - *Não* na FastTab **Permitir combinação de dimensões do produto** nos **Perfis de localização** *MASSA*, para que nenhuma dimensão do produto seja combinada. Nesse caso, quando você receber a ordem de compra, cada grade de produto será colocada em um novo local.