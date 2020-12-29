---
title: Recebimento da placa de licença por meio do aplicativo de depósito
description: Este tópico explica como configurar o aplicativo de depósito para oferecer suporte ao uso de um processo de recebimento de placa de licença para receber um estoque físico.
author: perlynne
manager: tfehr
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSParameters, WHSRFMenuItem, WHSLicensePlate, WHSPackingStructure
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 0d6894c0adb5671818e976dbb5116ecb947025d2
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422566"
---
# <a name="license-plate-receiving-via-the-warehouse-app"></a>Recebimento da placa de licença por meio do aplicativo de depósito

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar o aplicativo de depósito para oferecer suporte ao uso de um processo de recebimento de placa de licença para receber um estoque físico.

Você pode usar esta funcionalidade para registrar rapidamente o recebimento de um estoque de entrada relacionado a um aviso de embarque (ASN). O sistema automaticamente cria um ASN quando os processos de gerenciamento do depósito forem usados para remeter uma ordem de transferência. Para o processo da ordem de compra, um ASN pode ser registrado manualmente ou importado automaticamente usando um processo de entidade de dados do ASN de entrada.

Os dados do ASN são vinculados a cargas e remessas por meio de *estruturas de embalagem*, nas quais os paletes (placas de licença pai) podem conter caixas (placas de licença aninhadas).

> [!NOTE]
> Para reduzir o número de transações de estoque quando estruturas de embalagem com placas de licença aninhadas forem usadas, o sistema registra o estoque físico disponível na placa de licença pai. Para acionar a movimentação do estoque físico disponível da placa de licença pai para as placas de licença aninhadas, com base nos dados de estrutura de embalagem, o dispositivo móvel deve fornecer um item de menu baseado no processo de criação de trabalho *Empacotar em placas de licença aninhadas*.

## <a name="warehousing-mobile-device-app-processing"></a>Processamento do aplicativo de dispositivo móvel do depósito

Quando um trabalhador digitaliza uma ID da placa de licença recebida, o sistema inicializa um processo de recebimento da chapa de licença. Com base nessas informações, o conteúdo da placa de licença (dados provenientes do ASN) é registrado fisicamente no local da doca de entrada. Os fluxos a seguir dependerão de suas necessidades de processo comercial.

## <a name="work-policies"></a>Políticas de trabalho

Como ocorre com (por exemplo) o processo de item de menu de dispositivo móvel *Relatar como concluído*, o processo de recebimento da placa de licença oferece suporte a vários fluxos de trabalho com base na configuração definida.

### <a name="work-policies-with-work-creation"></a>Políticas de trabalho com criação de trabalho

Quando você registra itens de entrada usando uma política de trabalho que cria trabalho, o sistema gera e salva registros de trabalho armazenados para cada registro. Se você usar o processo de trabalho *Recebimento e armazenamento de placa de licença*, então o registro e o armazenamento serão tratados como uma única operação usando um único item de menu de dispositivo móvel. Se você usar o processo *Recebimento da placa de licença*, os processos de recebimento e de armazenamento são tratados como duas operações de depósito diferentes, cada uma com seu próprio item de menu de dispositivo móvel.

### <a name="work-policies-without-work-creation"></a>Políticas de trabalho sem criação de trabalho

Você pode usar o processo de recebimento da placa de licença sem criar trabalho. Se você definir políticas de trabalho que tenham um tipo de ordem de trabalho de *Recebimento de transferência* e/ou *Ordens de compra*, e usar o processo para *Recebimento de placa de licença (e armazenamento)*, os dois processos do Warehouse Mobile App não criarão trabalhos. Em vez disso, eles apenas registram o estoque físico de entrada na placa de licença na doca de recebimento de entrada.

- *Recebimento da placa de licença*
- *Recebimento e armazenamento da placa de licença*

> [!NOTE]
> - Você deve definir pelo menos um local para uma política de trabalho na seção **Locais de estoque**. Não é possível especificar a mesma localização para várias políticas de trabalho.
> - A opção **Imprimir etiqueta** para os itens de menu do dispositivo móvel de depósito não imprimirá uma etiqueta de placa de licença sem criação de trabalho.

Para disponibilizar essa funcionalidade no seu sistema, você deverá ativar o recurso *Aprimoramentos de recebimento de placa de licença* no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="receive-inventory-on-a-location-that-doesnt-track-license-plates"></a>Receber estoque em um local que não rastreie placas de licença

É possível usar uma localização de depósito atribuída a um perfil de local, mesmo quando o **Usar rastreamento da placa de licença** não está ativado. Portanto, ao receber o estoque, você poderá registrar diretamente o estoque disponível em um local sem criação de trabalho.

## <a name="add-mobile-device-menu-items-for-each-receiving-location-in-a-warehouse"></a>Adicionar itens de menu de dispositivo móvel para cada local de recebimento em um depósito

O recurso *Aprimoramentos de recebimento de placa de licença* permite que você receba em qualquer local de um depósito adicionando itens de menu de recebimento de placa de licença específico do local (e armazene) ao Warehouse Mobile App. Anteriormente, o sistema tem suporte para receber somente no local padrão definido para cada depósito. No entanto, quando esse recurso está ativado, os itens de menu do dispositivo móvel para recebimento de placa de licença (e armazenado) agora fornecem a opção **Usar dados padrão**, que permite selecionar um local "para" personalizado para cada item de menu. (Esta opção já estava disponível para alguns outros tipos de itens de menu.)

Para disponibilizar essa funcionalidade no seu sistema, você deverá ativar o recurso *Aprimoramentos de recebimento de placa de licença* no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="show-or-skip-the-receiving-summary-page"></a>Mostrar ou ignorar a página de resumo do recebimento

Você pode usar o recurso *Controlar a exibição de uma página de resumo do recebimento em dispositivos móveis* para usar um fluxo de aplicativo adicional detalhado do Depósito como parte do processo de recebimento da placa de licença.

Quando este recurso estiver ativado, os itens do menu do dispositivo móvel do recebimento da placa de licença ou do recebimento e armazenamento da placa de licença fornecerão uma configuração para **Exibir página de resumo do recebimento**. Essa configuração tem as seguintes opções:

- **Exibir um resumo detalhado** – Durante o recebimento da placa de licença, os trabalhadores verão uma página extra que mostra as informações completas do ASN.
- **Ignorar o resumo** – Os funcionários não verão as informações completas do ASN. Os trabalhadores de depósito também não poderão definir um código de disposição nem adicionar exceções durante o processo de recebimento.

Para tornar esta funcionalidade disponível no sistema, você deve ativar o recurso *Controlar se é necessário exibir uma página de resumo de recebimento em dispositivos móveis* no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino

Um processo de recebimento de placa de licença não pode ser usado se o ASN contiver uma ID de placa de licença já existente e dados físicos disponíveis em um local de depósito diferente do local de depósito no qual o registro da placa de licença ocorre.

Para cenários de ordem de transferência nos quais o depósito de trânsito não rastreia placas de licença (e, portanto, não rastreia o estoque físico disponível por placa de licença), é possível usar o recurso *Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino* para impedir atualizações de placas de licença físicas disponíveis que ainda estão em trânsito.

Para disponibilizar essa funcionalidade no seu sistema, você deverá ativar o recurso *Impedir que placas de licença remetidas em ordem de transferência sejam usadas em depósitos diferentes do que o depósito de destino* no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Para gerenciar a funcionalidade quando esse recurso estiver disponível, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Geral** no FastTab **Placas de licença**, defina o campo **Política da placa de licença do depósito de trânsito** com um dos seguintes valores:

    - **Permitir reutilização de placa de licença não rastreada** – O sistema funciona da mesma forma quando o recurso *Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino* não está disponível. Esse valor é a configuração padrão quando você ativa o recurso pela primeira vez.
    - **Impedir a reutilização de placa de licença não rastreada** – Somente as atualizações disponíveis relacionadas a uma placa de licença remetida serão permitidas no depósito de destino até que a ordem de transferência tenha sido recebida.

## <a name="more-information"></a>Mais informações

Para obter mais informações sobre itens do menu do dispositivo móvel, consulte [Configurar dispositivos móveis para trabalho de depósito](configure-mobile-devices-warehouse.md).

Para obter mais informações sobre o cenário de produção de *Relatar como concluído*, consulte a [Visão geral de políticas de trabalho de depósito](warehouse-work-policies.md).

Para obter mais informações sobre o gerenciamento de carga de entrada, consulte [Manuseio de depósito de cargas de entrada para ordens de compra](inbound-load-handling.md).
