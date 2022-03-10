---
title: Configurar ativos fixos
description: Este tópico fornece uma visão geral da configuração do módulo de ativos fixos.
author: moaamer
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13771
ms.assetid: 8be64197-fea1-4a34-8af2-d939919c28b1
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 572d104bbc7024da1ea4b219fd3f544f36a88ccddcf1aa5d18065e2e08b93bfa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754209"
---
# <a name="set-up-fixed-assets"></a>Configurar ativos fixos

[!include [banner](../includes/banner.md)]

Este tópico fornece uma visão geral da configuração do módulo de **Ativos fixos**. 

Comportamento geral de controle de parâmetros no módulo Ativos fixos. Grupos de ativos fixos permitem agrupar seus ativos e especificar atributos padrão para cada ativo atribuído a um grupo. Livros são atribuídos a grupos de ativos fixos. Os livros acompanham o valor financeiro de um ativo fixo ao longo de tempo usando a configuração depreciação definida no perfil de depreciação.

Ativos fixos são atribuídos a um grupo de itens ao serem criados. Por padrão, os ativos atribuídos - grupo de ativo fixo são alocados no fixos - ao ativo fixo. Os livros definidos para o lançamento na contabilidade são associados a um perfil de postagem. Contas contábeis são definidas para cada registro no perfil de lançamento e são usadas quando transações de ativos fixos são lançadas.

![Componentes de ativos fixos.](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Perfis de depreciação

Você deve configurar os perfis de depreciação primeiro. O perfil de depreciação, você define como o valor de um ativo é depreciado com o tempo. Você deve definir o método de depreciação, o ano de depreciação (ano civil ou ano fiscal), e a frequência de depreciação. Para saber mais, consulte [Configurar e criar perfis de depreciação](tasks/set-up-depreciation-profiles.md).

## <a name="books"></a>Registros

Após os perfis configurados de depreciação, você deve criar registros necessários para os ativos. Cada livro controla um ciclo de vida financeiro independente de um ativo. Os registros podem ser configurados para lançar transações associadas à contabilidade. Esta configuração é a configuração padrão, porque é usado normalmente para relatórios financeiros corporativo. Os registros que não são da contabilidade para lançar somente fixo sub-razão de ativo e geralmente é usado para o relatório de imposto com.

Um perfil de depreciação principal está atribuído a cada registro. Os registros também têm um perfil de depreciação alternativo ou de alternativa, se este tipo de perfil é aplicável. Para incluir automaticamente o registro em execuções de depreciação de ativos, você deve habilitar a opção **Calcule a depreciação**. Se essa opção não estiver habilitada para um ativo, a proposta de depreciação o ignora.

Você também pode configurar livros derivados. As transações derivadas especificadas são lançadas nos registros derivados como uma cópia exata da transação principal. Portanto, as transações derivadas são normalmente configuradas para aquisições e eliminações, não para transações de depreciação. Para obter mais informações, consulte [Configurar modelos de valor](tasks/set-up-value-models.md).

Uma opção na página **Parâmetros de ativos fixos** permite ativar ou desativar a funcionalidade de bloqueio. Este recurso é habilitado no **Espaço de trabalho de gerenciamento de recursos**.

## <a name="fixed-asset-posting-profiles"></a>Perfis de lançamentos de ativo fixo

Depois de configurar os registros, você pode criar o perfil de lançamentos. O perfil de postagem deve ser definido por registro, mas também pode ser definida no nível mais detalhado. Por exemplo, defina o perfil de postagem da combinação de um registro e o grupo de ativos, ou até para alguém fixo de um registro de ativo fixo. Por padrão, as contas contábeis definidas são usadas para o ativo fixo transações de ativos.

Defina as contas contábeis usadas durante os processos de eliminação, vendas de eliminação e sucatas de eliminação. No momento da alienação, as transações de ativos fixos lançadas anteriormente são revertidas das contas originais. Os valores líquidos então são movidos para a conta apropriada para ganhos e perdas para alienação de ativo. Para ajudar a garantir que as transações são revertidas corretamente, você deve configurar para cada tipo de transação que você utiliza em sua empresa. A conta principal deve ser a principal original para esse tipo de transação no perfil de lançamento, em contrapartida, deve ser a conta de ganhos e perdas. A exceção é o valor líquido contábil. Nesse caso, a conta principal e a contrapartida devem ser definidas para lucro e a perda da conta de eliminação. Para obter mais informações, consulte [Configurar perfis de lançamento de ativos fixos](tasks/set-up-fixed-asset-posting-profiles.md).

## <a name="fixed-asset-groups"></a>Grupos de ativos fixos

O campo **Grupo de ativos fixos** é o único campo obrigatório ao criar um ativo fixo. O valor deste campo determina o valor padrão de vários campos informativos para o ativo. Os registros são configurados de forma que um registro padrão é atribuído a cada ativo em um grupo. Assim, os atributos que você define para os registros podem ser específicos a um grupo de ativos. Esses atributos incluem a vida útil e a convenção de depreciação.

Você também pode definir provisões de depreciação especial, ou depreciação extra, uma combinação específica de um grupo de ativo e um registro. Atribua uma prioridade a provisão para depreciação especial para especificar a ordem em que as permissões serão calculadas quando em várias permissões atribuídas a um registro. Para obter mais informações, consulte [Configurar grupos de ativos fixos](tasks/set-up-fixed-asset-groups.md).

## <a name="journal-names"></a>Nomes de diário

Na página **Nomes de diário**, você deve criar os nomes de diário que devem ser usados com o diário de ativos fixos. Você deve definir o campo **Tipo de diário** para **Lançar ativos fixos**. Defina o campo **Série de comprovante** de forma que os nomes de diário sejam usados para o diário de ativos fixos. Os diários de ativos fixos não devem usar a configuração **Apenas um número de comprovante**, pois um número de comprovante exclusivo é necessário para diversos processos automatizados, como transferências e divisões.

## <a name="fixed-asset-parameters"></a>Parâmetros do ativo fixo

A última etapa será atualizar os parâmetros de ativo fixo.

O campo **Limite de capitalização** determina se os ativos são depreciados. Se uma linha de compra for selecionada como ativo, mas não atender ao limite de capitalização especificado, um ativo fixo ainda é criada ou atualizada, mas **Calcule a depreciação** a opção é definida em **Não**. Portanto, o ativo não é depreciado automaticamente como parte das propostas de depreciação.

Uma opção importante é chamada **Criar automaticamente valores de ajuste da depreciação com alienação**. Quando você define essa opção como **Sim**, a depreciação do ativo é ajustada automaticamente, com base nas configurações de depreciação no momento da alienação do ativo. Outra opção permite deduzir descontos à vista do valor de aquisição quando você adquire ativos fixos usando uma fatura de fornecedor.

O parâmetro **Bloquear livros de ativos em um diário de depreciação** permite que você bloqueie livros de ativos em um diário de depreciação. Quando as transações de depreciação estão sendo lançadas, o sistema verificará se o mesmo livro de ativos não foi adicionado a mais de um diário de depreciação. Se sim, esse livro de ativos será bloqueado e o lançamento será interrompido. Se uma ID do livro de ativos estiver em um diário bloqueado, ela será desbloqueada automaticamente quando o lançamento for concluído para o diário original. Você também pode desbloquear o diário manualmente. 

Na Guia Rápida **Ordens de compra**, você pode configurar como deseja que os ativos sejam criados como parte do processo de compra. A primeira opção é chamada **Permitir a aquisição de ativos de Compras**. Se você definir esta opção como **Sim**, a aquisição de ativo quando a nota fiscal ocorre é lançada. Se você definir esta opção como **Não**, você ainda pode colocar um ativo em uma ordem de compra (PO) e a nota fiscal, mas a aquisição não será lançado. O lançamento deve ser feito como uma etapa separada do diário de ativos fixos. A opção **Criar um ativo durante o recebimento de produtos ou o lançamento de fatura** permite criar um novo ativo “no transporte” durante o lançamento. Portanto, o ativo não precisa ser configurado como um ativo fixo antes da transação. A última opção, **Cheque para a criação de ativos fixos durante a entrada linha** se aplica, somente as requisições de compra.

Você pode configurar códigos razão que são necessários para alterações em um ativo fixo ou para transações de ativo fixo específicas.

Por fim, na guia **Sequências numéricas**, defina sequências numéricas para ativos fixos. A sequência numérica do **Ativo fixo** pode ser substituída pela sequência numérica do **Grupo de ativos fixos** se tiver sido especificada.

Para saber mais, consulte [Criar um ativo fixo](tasks/create-fixed-asset.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
