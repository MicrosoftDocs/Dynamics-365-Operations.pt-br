---
title: Crie um ativo
description: Este tópico descreve como criar um ativo em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5c77f32caad5e2e79cbc0e21f72a3daa79acecb
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3274156"
---
# <a name="create-an-asset"></a>Crie um ativo

[!include [banner](../../includes/banner.md)]

 

Este tópico descreve como criar um ativo em Gerenciamento de Ativos.

1. Clique em **Gerenciamento de ativos** > **Comum** > **ativos** > **Todos os ativos** ou **Ativos ativos**.
2. Clique no botão **Novo**.
3. Na caixa de diálogo **Criar ativos**, insira dados sobre o **Ativo** (a ID do ativo) e o nome do ativo. Selecione a data e a hora do ativo no campo **Efetivo**. A partir dessa data, é possível instalar o ativo em um local funcional bem como mover e substituir o ativo em uma estrutura de ativos.
4. No campo **Tipo de ativo**, selecione o tipo de ativo para o ativo (campo obrigatório). Se necessário, selecione **Fabricante do ativo** e **Modelo de ativo** para o ativo. Se apenas um produto foi configurado, esse produto será automaticamente selecionado no campo **Fabricante de ativo**. As seleções disponíveis nos campos **Fabricante de ativo** e **Modelo de ativo** dependem da configuração em [Fabricantes e modelos de ativo](../setup-for-objects/product-and-model.md).
5. No grupo **Ativo pai**, o campo **Ativo** está em branco como padrão. Se necessário, selecione um ativo pai e todos os campos no grupo **Ativo pai** serão preenchidos automaticamente.
    >[!NOTE]  
    >Quando você seleciona um ativo principal, duas ou três guias estão disponíveis: a guia **Meus ativos** contém os ativos relativos aos locais funcionais em que você (o trabalhador de manutenção registrado no sistema) deve ser alocado. Se nenhum local funcional for configurado em um funcionário de manutenção no formulário [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md), a guia **Meus ativos** não ficará visível. A guia **Ativos ativos** contém uma lista de todos os ativos com o estado de ciclo de vida do ativo "Ativo". A guia **Exibição de ativo** exibe um modo de exibição de árvore dos locais funcionais e ativos instalados nesses locais.

6. O local funcional padrão que você configurou é sugerido para o ativo no grupo **Ativo** > campo **Local funcional**. Selecione outro local funcional, se necessário.

    >[!NOTE]
    >Após criar um ativo, você poderá instalá-lo em outro local funcional, se necessário. Apenas os ativos em nível superior (ativos sem um ativo pai atual) podem ser instalados em um local funcional. Isso significa que você instala o nível superior bem como todos os ativos filho no local funcional selecionado. Leia mais sobre como instalar ativos em locais funcionais em [Introdução a locais funcionais](../functional-locations/introduction-to-functional-locations.md).

7. Clique em **OK**.
8. Selecione o ativo na lista **Todos os Ativos** e clique no botão **Editar** para adicionar mais informações ao ativo.

## <a name="general-information"></a>Informações gerais

O local funcional ao qual o ativo está relacionado aparece no campo **Local funcional**. Se o ativo for um ativo pai, o número de filhos relacionadas ao ativo será mostrado no campo **Filho**. Se o ativo for um subativo de um ativo existente, a ID do ativo pai será mostrada no campo **Pai**.

Você pode editar as informações **Fabricante do ativo** e **Modelo de ativo** no ativo, que são usadas para gerenciar peças sobressalentes, peças sobressalentes alternativas e padrões de tipo de trabalho. Consulte [Fabricantes e modelos de ativo](../setup-for-objects/product-and-model.md) para obter mais informações. Você também pode adicionar informações sobre **Ano do modelo** e **Número de série**, se necessário.

**Estado do ciclo de vida atual** é usado para definir se o ativo está ativo ou inativo. Ao criar um ativo, o estágio é sempre definido como o primeiro estágio no grupo de estágios do ativo. Quando você estiver pronto para ativar um ativo, clique em **Atualiza estado do ativo**, selecione o estado do ciclo de vida definido como "ativo ativo" e clique em **OK**.

**Observação:** Quando um ativo estiver definido como "inativo", não será mais possível criar ordens de serviço para o ativo. Além disso, você não pode agendar trabalhos de manutenção preventiva para um valor inativo.

Os campos **Nível de serviço** e **Severidade** estão relacionados a ordens de serviço criadas para o ativo. Os campos mostram os números de **Nível de serviço** e **Severidade** calculados para a configuração atual do ativo. Consulte [Níveis de serviço de ativo](../setup-for-objects/object-priorities.md) e [Tipos de severidade de ativo](../setup-for-objects/object-criticalities.md) em relação à configuração desses valores.

## <a name="asset"></a>Ativo

Você pode selecionar um **Recurso** para o ativo. A seleção do recurso determina o calendário que é usado para o agendamento da ordem de serviço. A seleção do recurso costuma ser usada para ativos fixos. Os recursos e grupos de recursos são configurados em **Administração da organização** > **Recursos** > **Grupos de recursos** ou **Recursos**.

No campo **Número de ativos fixos**, selecione um ativo fixo a ser relatado no ativo. Isso será relevante caso o ativo esteja relacionada a um projeto de investimento.

- Se o ativo estiver relacionada a um ativo fixo, você poderá criar um tipo de ordem de serviço a ser usado para ordens de serviço relativas a um projeto de investimento. 
- Informações sobre ativos fixos para um ativo estão relacionadas ao módulo **Ativos fixos** no Dynamics 365 Supply Chain Management. Isso significa que, em **Ativos fixos** > **Ativos fixos** > **Ativos fixos**, você pode obter uma visão geral de projetos de Gerenciamento de Ativos que podem estar relacionados a um ativo fixo, selecionando o ativo da lista e exibindo o conteúdo no painel **Informações relacionadas** > seção **Projetos associados**.


## <a name="details"></a>Detalhes

No campo **Data inicial de ativação**, aparece a data em que você atualizou o estado do ciclo de vida do ativo em um estado ativo (consulte [Estados do ciclo de vida de ativo](../setup-for-objects/object-stages.md) em relação à configuração de estados do ciclo de vida do ativo). Se o ativo não estiver mais ativo e você tiver atualizado o estado do ciclo de vida do ativo para um estado do ciclo de vida inativo, a data final de ativação do ativo aparecerá no campo **Data final de ativação**. Se necessário, você poderá alterar manualmente essas datas.

Se necessário, você poderá inserir uma data esperada para substituição do ativo no campo **Data de substituição**. Um valor previsto para substituir o ativo pode ser inserido no campo **Valor de substituição**. Exemplo: Você poderá usar informações de substituição para compará-lo com os custos de manutenção de um ativo e tomar uma decisão de compras de um novo ativo se os custos de manutenção no ativo existente aumentarem rapidamente.

## <a name="notes"></a>Observação

Você pode adicionar notas relacionadas ao ativo na Guia Rápida **Notas**. Clique no botão **Adicionar o carimbo de data/hora** antes de escrever a nota se desejar adicionar informações de usuário e uma data/carimbo de data/hora na nota.

## <a name="attributes"></a>Atributos

Nesta Guia Rápida, defina valores para atributos de ativo. Esses atributos podem ser usados para descrever propriedades ou características pertinentes ao ativo; por exemplo, tamanho, peso ou configuração do computador.

Clique em **Adicionar linha** e selecione o tipo de atributo. Em seguida, insira o **Valor** relacionado ao tipo de atributo e salve o registro.

>[!NOTE] 
>Você pode obter uma visão geral de tipos de atributo de ativo e sua relação com os ativos em **Atributo de ativo** e **Visão geral de atributo de ativo**. Consulte [Visão geral de atributo de ativo](../objects/object-specification-overview.md) para obter mais informações.

## <a name="vendor"></a>Fornecedor

Na Guia Rápida **Fornecedor**, selecione uma conta de fornecedor para o ativo. Além disso, se uma garantia do fornecedor foi concedida, você poderá inserir informações de garantia aqui.

## <a name="address"></a>Endereço

Na Guia Rápida **Endereço**, você pode inserir o endereço do equipamento. Se nenhum endereço for inserido no ativo, o ativo usará o endereço de um ativo pai se o ativo pai tiver um endereço. Se nenhum endereço estiver relacionado ao ativo ou a pais na hierarquia de ativos, o endereço do local funcional em que o ativo é instalado poderá ser usado. Se esse local funcional não tiver um endereço relacionado a ela, o endereço do local funcional pai será usado no ativo.

## <a name="asset-management-plans"></a>Planos de gerenciamento de ativos

Os planos de manutenção são usados para agendar trabalhos de manutenção preventiva em intervalos regulares no ativo. Nesta Guia Rápida, você pode configurar linhas de plano de manutenção para o ativo selecionado. Os rounds de manutenção podem ser configurados para vários ativos, em que você precisa realizar uma tarefa semelhante em intervalos regulares. Na guia **Planos de manutenção de locais funcionais**, aparecem os planos de manutenção relacionados ao local funcional em que o ativo é instalado.

>[!NOTE]
>Se você excluir uma linha do plano de manutenção ou um round de manutenção relacionado a um ativo em **Todos os Ativos**, também excluirá automaticamente todas as agendas de manutenção com o status "Criado" que foram criadas com base nesse plano ou round de manutenção.

## <a name="functional-location-maintenance-plans"></a>Planos de manutenção do local funcional

Nesta Guia Rápida, você obtém uma visão geral dos planos de manutenção relacionados ao local funcional em que o ativo é instalado.

## <a name="maintenance-rounds"></a>Rounds de manutenção

Nesta Guia Rápida, você pode adicionar ou remover rounds de manutenção, que estão relacionados aos ativos.

## <a name="financial-dimensions"></a>Dimensões financeiras

Você pode selecionar dimensões financeiras para o ativo.
