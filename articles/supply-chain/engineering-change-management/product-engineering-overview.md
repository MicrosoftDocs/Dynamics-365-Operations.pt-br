---
title: Visão geral do gerenciamento de alterações de engenharia
description: Este tópico fornece uma visão geral do gerenciamento de alterações de engenharia, que ajuda a planejar e gerenciar o controle de versão de produtos e gerenciar ciclos de vida de produtos e alterações de engenharia.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
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
ms.openlocfilehash: b081cd8d56217b8cf76db824c29482d453fc9ea3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001939"
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

## <a name="turn-on-engineering-change-management-for-your-system"></a>Ativar o gerenciamento de alterações de engenharia para o sistema

Primeiro, ative o gerenciamento de alterações de engenharia seguindo estas etapas.

1. Acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Verifique se há atualizações.
1. Ative o recurso denominado **Gerenciamento de Alterações de Engenharia**.

Em seguida, ative a chave de configuração do **Gerenciamento de Alterações de Engenharia** seguindo estas etapas.

1. Coloque seu sistema em modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Vá para **Administração de sistema \> Configurar \> Configuração de licença**.
1. Expanda o nó **Comércio** e marque a caixa de seleção **Gerenciamento de Alterações de Engenharia**.
1. Desative o modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
