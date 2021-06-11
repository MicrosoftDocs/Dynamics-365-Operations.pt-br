---
title: Visão geral do gerenciamento de alterações de engenharia
description: Este tópico fornece uma visão geral do gerenciamento de alterações de engenharia, que ajuda a planejar e gerenciar o controle de versão de produtos e gerenciar ciclos de vida de produtos e alterações de engenharia.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d9430fe02abe58f37d2bfd1431b4da61527d0834
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115040"
---
# <a name="engineering-change-management-overview"></a>Visão geral do gerenciamento de alterações de engenharia

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Resumo do recurso

Os fabricantes de hoje precisam de um forte gerenciamento de dados de produtos, controle de versão e gerenciamento de alterações de engenharia para serem bem-sucedidos em um mundo com ciclos de vida de produtos cada vez menores, requisitos de qualidade e confiabilidade maiores e um foco maior na segurança dos produtos.

O gerenciamento de alterações de engenharia traz estrutura e disciplina para o processo de gerenciamento de dados de produtos e permite que os produtos sejam definidos, liberados e revisados de forma controlada com suporte dos fluxos de trabalho. Por meio de versões do produto e do gerenciamento de alterações de engenharia, você pode documentar, avaliar o impacto e aplicar alterações de engenharia durante todo o ciclo de vida de um produto.

O gerenciamento de alterações de engenharia ajuda a planejar e gerenciar o controle de versão de produtos e gerenciar ciclos de vida de produtos e alterações de engenharia. Veja uma lista dos principais recursos:

- Controle de versão de produtos
- Funcionalidade aprimorada de liberação de produtos que permite manter os dados mestres dos produtos em uma entidade legal (a empresa de engenharia) e publicar o produto liberado totalmente configurado em outras entidades legais
- Regras para validar que as informações necessárias foram inseridas antes de uma versão de produto ser ativada (verificações de preparação)
- Gerenciamento aprimorado do ciclo de vida de produtos por meio de um controle refinado sobre quando um produto liberado pode ser usado em processos empresariais específicos
- Solicitações de alterações de engenharia com suporte dos fluxos de trabalho
- Ordens de alterações de engenharia com suporte dos fluxos de trabalho

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

O vídeo anterior ([Recursos de gerenciamento de alterações no Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) está incluído na [playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a>Ativar os recursos de gerenciamento de alterações de engenharia e dimensão de versão para o seu sistema

Para poder usar o gerenciamento de alterações de engenharia, você deve habilitar o recurso *Gerenciamento de Alterações de Engenharia* e sua chave de configuração. Se você quiser rastrear a dimensão de versão dos produtos nas transações (opcional), também deverá habilitar o recurso *Dimensão de versão do produto* e sua chave de configuração.

Primeiro, ative os recursos seguindo estas etapas.

1. Acesse o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Verifique se há atualizações.
1. Ative o recurso denominado *Gerenciamento de Alterações de Engenharia*.
1. Se quiser usá-lo, ative também o recurso denominado *Versão de dimensão do produto*.

Em seguida, ative as chaves de configuração seguindo estas etapas.

1. Coloque seu sistema em modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Vá para **Administração de sistema \> Configurar \> Configuração de licença**.
1. Expanda o nó **Comércio**.
1. Habilite a chave de configuração para o recurso principal, marcando a caixa de seleção **Gerenciamento de Alterações de Engenharia**.
1. Expanda o nó **Gerenciamento de Alterações de Engenharia** e marque ou desmarque as seguintes caixas de seleção conforme necessário (dependendo dos recursos que deseja usar):

    - **Pesquisa de atributos**: marque esta caixa de seleção para habilitar o [recurso de pesquisa de atributos](engineering-attributes-and-search.md). Recomendamos habilitar esse recurso, mas você pode desmarcar essa caixa de seleção se não quiser usá-lo.
    - **Gerenciamento de alterações para fabricação de processos**: marque esta caixa de seleção se desejar usar os recursos de gerenciamento de alterações de engenharia para gerenciar alterações em fórmulas para fabricação de processos. Se você não precisa gerenciar fórmulas, pode desmarcar esta caixa de seleção. Para obter mais informações, consulte [Gerenciar alterações nas fórmulas e seus ingredientes](manage-formula-changes.md).

1. Se também quiser usar a dimensão de versão, marque a caixa de seleção **Dimensão do produto - Versão**. (Esta caixa de seleção está mais abaixo na lista, não aninhada no nó **Gerenciamento de Alterações de Engenharia**.)
1. Desative o modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

> [!IMPORTANT]
> A partir de abril de 2022, as chaves de licença de **Gerenciamento de Alterações de Engenharia** e **Dimensão do produto - Versão** serão habilitadas por padrão para todas as novas instalações, mas você ainda poderá desabilitá-las, se necessário.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
