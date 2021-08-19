---
title: Os registros de clientes não aparecem no Commerce Headquarters
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando os registros de clientes não aparecem imediatamente no Commerce Headquarters.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f551f94cec71ba7d740756c383b55741e9f8d42e20e63846ea6242383dc3ba32
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733884"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>Os registros de clientes não aparecem no Commerce Headquarters

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientações de solução de problemas que podem ajudar quando os registros de clientes não aparecem imediatamente no Commerce Headquarters.

## <a name="description"></a>descrição

Quando você cria um novo registro de cliente usando o fluxo de inscrição na vitrine de comércio eletrônico, o registro do cliente correspondente não aparece imediatamente no Commerce Headquarters.

## <a name="resolution"></a>Resolução

### <a name="disable-customer-creation-in-async-mode"></a>Desabilitar a criação de clientes no modo assíncrono

> [!IMPORTANT]
> Se você desabilitar a criação assíncrona de clientes, o desempenho do sistema poderá ser afetado, pois a criação de cada registro produzirá uma solicitação em tempo real para o Commerce Headquarters. Além disso, se o Commerce Headquarters estiver inoperante (por exemplo, durante os fluxos de serviço), todos os novos fluxos de criação de clientes produzirão erros.

Para desabilitar a criação de clientes no modo assíncrono no Commerce Headquarters, siga estas etapas.

1. Acesse **Varejo e Comércio \> Configuração de canal \> Configuração da loja online \> Perfis de funcionalidade**.
1. Se ainda não estiver usando um perfil de funcionalidade para seu canal online, crie um.
1. Verifique se a opção **Criar cliente no modo assíncrono** foi definida como **Não**.
1. Acesse **Varejo e Comércio \> Canais \> Lojas online**.
1. Selecione a loja online para desabilitar a criação assíncrona de clientes.
1. Na guia **Geral**, verifique se o campo **Perfil de funcionalidade** foi definido como o perfil de funcionalidade que você está usando para seu canal online.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário de B2C no Commerce](../set-up-b2c-tenant.md)
