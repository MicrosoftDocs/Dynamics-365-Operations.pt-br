---
title: Recebimento da placa de licença por meio do aplicativo do depósito
description: Este tópico explica como configurar o aplicativo de depósito para oferecer suporte ao uso de um processo de recebimento de placa de licença para receber um estoque físico.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 7d5ac6598ab80ece0164d7c92f5d84e91d21b385
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346367"
---
# <a name="license-plate-receiving-via-the-warehousing-app"></a>Recebimento da placa de licença por meio do aplicativo do depósito

Este tópico explica como configurar o aplicativo de depósito para oferecer suporte ao uso de um processo de recebimento de placa de licença para receber um estoque físico.

Você pode usar esta funcionalidade para registrar rapidamente o recebimento de um estoque de entrada relacionado a um aviso de embarque (ASN). O sistema automaticamente cria um ASN quando os processos de gerenciamento do depósito forem usados para remeter uma ordem de transferência. Para o processo da ordem de compra, um ASN pode ser registrado manualmente ou importado automaticamente usando um processo de entidade de dados do ASN de entrada.

Os dados do ASN são vinculados a cargas e remessas por meio de *estruturas de embalagem*, nas quais os paletes (placas de licença pai) podem conter caixas (placas de licença aninhadas).

> [!NOTE]
> Para reduzir o número de transações de estoque quando estruturas de embalagem com placas de licença aninhadas forem usadas, o sistema registra o estoque físico disponível na placa de licença pai. Para acionar a movimentação do estoque físico disponível da placa de licença pai para as placas de licença aninhadas, com base nos dados de estrutura de embalagem, o dispositivo móvel deve fornecer um item de menu baseado no processo de criação de trabalho *Empacotar em placas de licença aninhadas*.

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a>Mostrar ou ignorar a página de resumo do recebimento

Você pode usar o recurso *Controlar a exibição de uma página de resumo do recebimento em dispositivos móveis* para usar um fluxo de aplicativo adicional detalhado do depósito como parte do processo de recebimento da placa de licença.

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, este recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Controlar a exibição de uma página de resumo do recebimento em dispositivos móveis*

Quando este recurso estiver ativado, os itens do menu do dispositivo móvel do recebimento da placa de licença ou do recebimento e armazenamento da placa de licença fornecerão uma configuração para **Exibir página de resumo do recebimento**. Essa configuração tem as seguintes opções:

- **Exibir um resumo detalhado** – Durante o recebimento da placa de licença, os trabalhadores verão uma página extra que mostra as informações completas do ASN.
- **Ignorar o resumo** – Os funcionários não verão as informações completas do ASN. Os trabalhadores de depósito também não poderão definir um código de disposição nem adicionar exceções durante o processo de recebimento.

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino

Um processo de recebimento de placa de licença não pode ser usado se o ASN contiver uma ID de placa de licença já existente e dados físicos disponíveis em um local de depósito diferente do local de depósito no qual o registro da placa de licença está sendo realizado.

Para cenários de ordem de transferência nos quais o depósito de trânsito não rastreia placas de licença (e, portanto, não rastreia o estoque físico disponível por placa de licença), é possível usar o recurso *Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino* para impedir atualizações de placas de licença físicas disponíveis que ainda estão em trânsito.

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, este recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino*

Para gerenciar a funcionalidade quando esse recurso estiver disponível, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Geral** no FastTab **Placas de licença**, defina o campo **Política da placa de licença do depósito de trânsito** com um dos seguintes valores:

    - **Permitir reutilização de placa de licença não rastreada** – O sistema funciona da mesma forma quando o recurso *Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino* não está disponível. Esse valor é a configuração padrão quando você ativa o recurso pela primeira vez.
    - **Impedir a reutilização de placa de licença não rastreada** – Somente as atualizações disponíveis relacionadas a uma placa de licença remetida serão permitidas no depósito de destino até que a ordem de transferência tenha sido recebida.

## <a name="more-information"></a>Mais informações

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

Para obter mais informações sobre itens do menu do dispositivo móvel, consulte [Configurar dispositivos móveis para trabalho de depósito](configure-mobile-devices-warehouse.md).
