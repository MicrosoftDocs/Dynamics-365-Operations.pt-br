---
title: Os registros do cliente não aparecem no Commerce headquarters
description: Este artigo fornece orientações de solução de problemas que podem ajudar quando os registros do cliente não aparecem imediatamente no Commerce headquarters.
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
ms.openlocfilehash: 5cdc96c9829be4d34e9346b2c99d300c2349bc41
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876536"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>Os registros do cliente não aparecem no Commerce headquarters

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientações de solução de problemas que podem ajudar quando os registros do cliente não aparecem imediatamente no Commerce headquarters.

## <a name="description"></a>descrição

Quando você cria um novo registro do cliente usando o fluxo de inscrição na vitrine de comércio eletrônico, o registro do cliente correspondente não aparece imediatamente no Commerce headquarters.

## <a name="resolution"></a>Resolução

### <a name="disable-customer-creation-in-async-mode"></a>Desabilitar a criação de clientes no modo assíncrono

> [!IMPORTANT]
> Se você desabilitar a criação assíncrona de clientes, o desempenho do sistema poderá ser afetado, pois a criação de cada registro produzirá uma solicitação em tempo real para o Commerce headquarters. Além disso, se o Commerce headquarters estiver inoperante (por exemplo, durante os fluxos de serviço), todos os novos fluxos de criação de clientes produzirão erros.

Para desabilitar a criação de clientes no modo assíncrono no Commerce headquarters, siga estas etapas.

1. Acesse **Varejo e Comércio \> Configuração de canal \> Configuração da loja online \> Perfis de funcionalidade**.
1. Se ainda não estiver usando um perfil de funcionalidade para seu canal online, crie um.
1. Verifique se a opção **Criar cliente no modo assíncrono** foi definida como **Não**.
1. Acesse **Varejo e Comércio \> Canais \> Lojas online**.
1. Selecione a loja online para desabilitar a criação assíncrona de clientes.
1. Na guia **Geral**, verifique se o campo **Perfil de funcionalidade** foi definido como o perfil de funcionalidade que você está usando para seu canal online.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário de B2C no Commerce](../set-up-b2c-tenant.md)
