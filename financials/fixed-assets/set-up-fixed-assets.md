---
title: Configurar ativos fixos
description: "Este tópico fornece uma visão geral da configuração do módulo de ativos fixos."
author: twheeloc
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13771
ms.assetid: 8be64197-fea1-4a34-8af2-d939919c28b1
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 668fea64810524e8ce0c3833d25656c026f2780a
ms.openlocfilehash: d16c9ca5740c27528d74800957f9b47984c135cd
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2017

---

# <a name="set-up-fixed-assets"></a>Configurar ativos fixos

[!include[banner](../includes/banner.md)]


Este tópico fornece uma visão geral da configuração do módulo de ativos fixos.

<a name="overview"></a>Visão Geral
--------
Comportamento geral de controle de parâmetros no módulo Ativos fixos.

Grupos de ativos fixos permitem agrupar seus ativos e especificar atributos padrão para cada ativo atribuído a um grupo. Livros são atribuídos a grupos de ativos fixos. Os livros acompanham o valor financeiro de um ativo fixo ao longo de tempo usando a configuração depreciação definida no perfil de depreciação.

Ativos fixos são atribuídos a um grupo de itens ao serem criados. Por padrão, os ativos atribuídos - grupo de ativo fixo são alocados no fixos - ao ativo fixo. Os livros definidos para o lançamento na contabilidade são associados a um perfil de postagem. Contas razão são definidas por registro no perfil de lançamento e são usadas quando transações de ativo fixo são lançadas. 

![FixedAssetsComponentsImage](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Perfis de depreciação
Você deve definir os perfis de depreciação primeiro. O perfil de depreciação, você define como o valor de um ativo é depreciado com o tempo. Você deve definir o método de depreciação, o ano de depreciação (ano civil ou ano fiscal), e a frequência de depreciação. Para saber mais, consulte [Configurar e criar perfis de depreciação](tasks/set-up-depreciation-profiles.md)

## <a name="books"></a>Registros
Após os perfis configurados de depreciação, você deve criar registros necessários para os ativos. Cada livro controla um ciclo de vida financeiro independente de um ativo. Os registros podem ser configurados para lançar transações associadas à contabilidade. Esta configuração é a configuração padrão, porque é usado normalmente para relatórios financeiros corporativo. Os registros que não são da contabilidade para lançar somente fixo sub-razão de ativo e geralmente é usado para o relatório de imposto com.

Um perfil de depreciação principal está atribuído a cada registro. Os registros também têm um perfil de depreciação alternativo ou de alternativa, se este tipo de perfil é aplicável. Para incluir automaticamente o registro em execuções de depreciação de ativos, você deve habilitar a opção Calcule a depreciação. Se essa opção não estiver selecionada para um ativo, a proposta de depreciação ignora o ativo.

Você também pode configurar livros derivados. As transações derivadas especificadas serão lançadas como uma cópia exata da transação principal nos registros derivados. Portanto, as transações derivadas são normalmente configuradas para aquisições e eliminações, não para transações de depreciação.
Para saber mais, consulte [Configurar registros](tasks/set-up-value-models.md).

## <a name="fixed-asset-posting-profiles"></a>Perfis de lançamentos de ativo fixo
Depois de configurar os registros, você pode criar o perfil de lançamentos. O perfil de postagem deve ser definido por registro, mas também pode ser definida no nível mais detalhado. Por exemplo, defina o perfil de postagem da combinação de um registro e o grupo de ativos, ou até para alguém fixo de um registro de ativo fixo. Por padrão, as contas contábeis definidas são usadas para o ativo fixo transações de ativos.

Defina as contas contábeis usadas durante os processos de eliminação, vendas de eliminação e sucatas de eliminação. No momento de eliminação, as transações de ativos lançadas anteriormente são revertidas das contas originais, e valores líquidos são movidas a conta apropriada para o lucro e perda para a alienação de ativo. Para ajudar a garantir que as transações são revertidas corretamente, você deve configurar para cada tipo de transação que você utiliza em sua empresa. A conta principal deve ser a principal original para esse tipo de transação no perfil de lançamento, em contrapartida, deve ser a conta de ganhos e perdas. A exceção é o valor líquido contábil. Nesse caso, a conta principal e a contrapartida devem ser definidas para lucro e a perda da conta de eliminação. Para saber mais, consulte [Configurar perfis de lançamento de ativos fixos](tasks/set-up-fixed-asset-posting-profiles.md)

## <a name="fixed-asset-groups"></a>Grupos de ativos fixos
Grupo de ativos fixos o único campo é necessário quando você cria um ativo fixo. O valor deste campo determina o valor padrão de vários campos informativos para o ativo. Os registros são configurados de forma que um registro padrão é atribuído a cada ativo em um grupo. Você poderá então definir atributos para os registros que seja específico de um grupo de ativos, e Convenção de depreciação como Vida útil.

Você também pode definir provisões de depreciação especial, ou depreciação extra, uma combinação específica de um grupo de ativo e um registro. Atribua uma prioridade a provisão para depreciação especial para especificar a ordem em que as permissões serão calculadas quando em várias permissões atribuídas a um registro. Para saber mais, consulte [Configurar grupos de ativos fixos](tasks/set-up-fixed-asset-groups.md)

## <a name="fixed-asset-parameters"></a>Parâmetros do ativo fixo
A última etapa será atualizar os parâmetros de ativo fixo.

O campo **Limite de capitalização** determina se os ativos são depreciados. Se uma linha de compra for selecionada como ativo, mas não atender ao limite de capitalização especificado, um ativo fixo ainda é criada ou atualizada, mas Calcule a depreciação a opção é definida em Não. Portanto, o ativo não é depreciado automaticamente como parte das propostas de depreciação.

Uma opção importante é **Criar automaticamente valores de ajuste da depreciação com alienação**. Quando você definir esta opção como **Sim**, a depreciação de ativo seja ajustado automaticamente, com base nas configurações de depreciação no momento de alienação de ativo. Outra opção permite deduzir descontos à vista do valor de aquisição quando você adquire ativos fixos usando uma nota fiscal de fornecedor.

Na Guia Rápida Ordens de compra, você pode configurar como deseja que os ativos sejam criados como parte do processo de compra. A primeira opção é Permitir a aquisição de ativos de Compras. Se você definir esta opção como Sim, a aquisição de ativo quando a nota fiscal ocorre é lançada. Se você definir esta opção como Não, você ainda pode colocar um ativo em uma ordem de compra (PO) e a nota fiscal, mas a aquisição não será lançado. A postagem deve ser inserido como uma etapa separada do diário de ativos fixos. A opção Crie o ativo durante o recebimento de produtos ou fatura a postagem permite criar um novo ativo “no transporte” durante a postagem, de modo que não tenha que ser liquidada um ativo fixo antes da transação. A última opção, Cheque para a criação de ativos fixos durante a entrada linha se aplica, somente as requisições de compra.

Você pode configurar códigos razão que são necessários para alterações em um ativo fixo ou para transações de ativo fixo específicas.

Finalmente, na guia Sequências numéricas, defina sequências numéricas para ativos fixos. A sequência numérica de ativos pode ser substituída pelo ativo fixo, a sequência numérica de grupo de ativo fixo se tiver sido especificada.

Para saber mais, consulte [Criar ativos fixos](tasks/create-fixed-asset.md).


