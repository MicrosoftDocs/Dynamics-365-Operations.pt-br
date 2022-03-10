---
title: Visão geral do gerenciamento de alteração de engenharia (contém vídeo)
description: Este tópico fornece uma visão geral do gerenciamento de alterações de engenharia, que ajuda a planejar e gerenciar o controle de versão de produtos e gerenciar ciclos de vida de produtos e alterações de engenharia.
author: t-benebo
ms.date: 01/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 54d91d009d70194dfc91c8c855e0088f9de01718
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103804"
---
# <a name="engineering-change-management-overview"></a>Visão geral do gerenciamento de alterações de engenharia

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Resumo do recurso

Os fabricantes de hoje precisam de um forte gerenciamento de dados de produtos, controle de versão e gerenciamento de alterações de engenharia para serem bem-sucedidos em um mundo com ciclos de vida de produtos cada vez menores, requisitos de qualidade e confiabilidade maiores e um foco maior na segurança dos produtos.

O gerenciamento de alterações de engenharia traz estrutura e disciplina para o processo de gerenciamento de dados de produtos e permite que os produtos sejam definidos, liberados e revisados de forma controlada com suporte dos fluxos de trabalho. Por meio de versões do produto e do gerenciamento de alterações de engenharia, você pode documentar, avaliar o impacto e aplicar alterações de engenharia durante todo o ciclo de vida de um produto.

O gerenciamento de alterações de engenharia ajuda a planejar e gerenciar o controle de versão de produtos e gerenciar ciclos de vida de produtos e alterações de engenharia. Veja uma lista dos principais recursos:

- Controle de versão de produtos
- Funcionalidade aprimorada de liberação de produtos que permite manter os dados mestres dos produtos em uma entidade legal (a empresa de engenharia) e publicar o produto liberado totalmente configurado em outras entidades legais
- Regras para validar que as informações necessárias foram inseridas antes de uma versão de produto ser ativada (verificações de preparação)
- Gerenciamento aprimorado do ciclo de vida de produtos por meio de um controle refinado sobre quando um produto liberado pode ser usado em processos empresariais específicos
- Solicitações de alterações de engenharia com suporte dos fluxos de trabalho
- Ordens de alterações de engenharia com suporte dos fluxos de trabalho

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HE6B]

O vídeo anterior ([Recursos de gerenciamento de alterações no Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) está incluído na [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.

## <a name="turn-on-the-engineering-change-management-features-for-your-system"></a>Ativar os recursos de gerenciamento de alterações de engenharia para o sistema

Para poder usar o gerenciamento de alterações de engenharia, você deve habilitar o recurso *Gerenciamento de Alterações de Engenharia* e sua chave de configuração. Se você quiser rastrear a dimensão de versão dos produtos nas transações (opcional), também deverá habilitar o recurso *Dimensão de versão do produto* e sua chave de configuração. Depois que esses pré-requisitos forem configurados conforme necessário, você poderá ativar recursos opcionais adicionais para o gerenciamento de alterações de engenharia.

### <a name="turn-the-basic-engineering-change-management-features-on-or-off"></a>Ativar ou desativar os recursos básicos de gerenciamento de alterações de engenharia

Para ativar ou desativar os recursos básicos de gerenciamento de alterações de engenharia, siga estas etapas. A partir do Supply Chain Management versão 10.0.25, o recurso *Gerenciamento de Alterações de Engenharia* está ativado por padrão.

1. Acesse o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Verifique se há atualizações.
1. Ative ou desative o recurso *Gerenciamento de Alterações de Engenharia*, conforme necessário.
1. Se você quiser rastrear a dimensão de versão dos produtos nas transações (opcional), ative o recurso *Dimensão de versão do produto*.

### <a name="turn-the-required-configuration-keys-on-or-off"></a>Ativar ou desativar as chaves de configuração necessárias

Em seguida, ative as chaves de configuração seguindo estas etapas. Elas não são ativadas por padrão.

1. Coloque seu sistema em modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Acesse **Administração de sistema \> Configurar \> Configuração de licença**.
1. Expanda o nó **Comércio**.
1. Habilite ou desabilite a chave de configuração para o recurso principal marcando a caixa de seleção **Gerenciamento de Alterações de Engenharia**.
1. Expanda o nó **Gerenciamento de Alterações de Engenharia** e marque ou desmarque as seguintes caixas de seleção conforme necessário (dependendo dos recursos que deseja usar):

    - **Pesquisa de atributos**: marque esta caixa de seleção para habilitar o [recurso de pesquisa de atributos](engineering-attributes-and-search.md). Recomendamos habilitar esse recurso, mas você pode desmarcar essa caixa de seleção se não quiser usá-lo.
    - **Gerenciamento de alterações para fabricação de processos**: marque esta caixa de seleção se desejar usar os recursos de gerenciamento de alterações de engenharia para gerenciar alterações em fórmulas para fabricação de processos. Se você não precisa gerenciar fórmulas, pode desmarcar esta caixa de seleção. Para obter mais informações, consulte [Gerenciar alterações nas fórmulas e seus ingredientes](manage-formula-changes.md).

1. Se também quiser usar a dimensão de versão, marque a caixa de seleção **Dimensão do produto - Versão**. (Esta caixa de seleção está mais abaixo na lista e não está aninhada no nó **Gerenciamento de Alterações de Engenharia**.) Você pode desmarcar essa caixa de seleção se não precisar desse recurso.
1. Desative o modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. O banco de dados deve ser sincronizado para garantir que as chaves de configuração estejam devidamente atualizadas para refletir as alterações. Execute uma das seguintes etapas, dependendo do tipo de ambiente em que estiver trabalhando:
    - **Para ambientes de nível 1 (desenvolvimento)**: abra seu projeto no Microsoft Visual Studio e, depois, selecione **Dynamics 365 \> Sincronizar banco de dados \> Sincronizar**.
    - **Para ambientes de nível 2 (e superior)**: o banco de dados é sincronizado automaticamente após você colocar e retirar o ambiente do modo de manutenção, de forma que possa ignorar esta etapa.

### <a name="turn-on-additional-engineering-change-management-features"></a>Ativar os recursos adicionais de gerenciamento de alterações de engenharia

Depois de ativar os recursos básicos de gerenciamento de alterações de engenharia e habilitar suas chaves de configuração, vários recursos adicionais e opcionais de gerenciamento de alterações de engenharia são adicionados ao gerenciamento de recursos. Cada um desses recursos está listado no módulo **Gerenciamento de alterações de engenharia**. A tabela a seguir descreve cada recurso opcional e fornece links para obter mais informações. A partir do Supply Chain Management versão 10.0.25, todos esses recursos são ativados por padrão, mas você ainda pode desativá-los.

| Nome do recurso no gerenciamento de recursos | Descrição | Estado do recurso |
|---|---|---|
| Habilitar gerenciamento de modificações em produtos existentes | <p>Este recurso permite converter produtos existentes em produtos de engenharia para que você possa começar a gerenciá-los usando o gerenciamento de alterações de engenharia.</p><p>Para obter mais informações, consulte [Habilitar o gerenciamento de alterações em produtos existentes](change-management-existing-products.md).</p> |
| Notificações de engenharia para produção | <p>Quando um produto é alterado na engenharia, pode ser importante notificar a produção sobre essas alterações. Dessa forma, os trabalhadores de produção podem executar a ação apropriada, como a substituição de componentes, a substituição da lista de materiais (BOM) ou a substituição de roteiros. Este recurso permite notificar a produção sobre alterações em produtos que estão sendo produzidos.</p><p>Para obter mais informações, consulte [Gerenciar alterações de produtos de engenharia](engineering-change-management.md).</p> |
| Herança de atributo aprimorada para Gerenciamento de Modificações de Engenharia | <p>Este recurso simplifica o gerenciamento de atributos para mercadorias concluídas ou itens intermediários. Quando esse recurso está ativado, é mais fácil identificar todos os atributos que pertencem a um item, e você pode selecionar os atributos que devem ser propagados desse item para seu item pai. Esse recurso é útil, por exemplo, quando um componente de uma mercadoria concluída é frágil, tóxico ou inflamável, porque você pode identificar facilmente o atributo frágil, tóxico ou inflamável e propagá-lo para a mercadoria concluída.</p><p>Para obter mais informações, consulte [Atributos de engenharia e pesquisa de atributos de engenharia](engineering-attributes-and-search.md).</p> |
| Verificações de preparação do produto | <p>Este recurso permite configurar verificações de preparação para produtos padrão (não de engenharia). Use as verificações de preparação do produto para garantir que cada produto seja totalmente definido e que todas as políticas necessárias sejam configuradas antes que o produto seja disponibilizado e usado em transações. Se você desabilitar esse recurso depois de usá-lo por um tempo, todas as verificações de preparação existentes para produtos padrão serão excluídas.</p><p>Para obter mais informações, consulte [Preparo do produto](product-readiness.md).</p> |
| Gerenciar modificações em fórmulas e seus ingredientes | <p>Este recurso permite rastrear alterações em ingredientes da fórmula, coprodutos e subprodutos.</p><p>Para obter mais informações, consulte [Gerenciar alterações nas fórmulas e seus ingredientes](manage-formula-changes.md).</p> |
| Geração de grades para produtos de engenharia | <p>Este recurso permite gerar grades para produtos de engenharia, com base nos valores de dimensão disponíveis.</p><p>Para obter mais informações, consulte [Gerar variantes para produtos de engenharia](engineering-variants.md).</p> |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
