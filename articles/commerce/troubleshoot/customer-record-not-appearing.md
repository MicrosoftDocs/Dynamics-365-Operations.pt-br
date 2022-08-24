---
title: Os registros do cliente não aparecem no Commerce headquarters
description: Este artigo fornece orientações de solução de problemas que podem ajudar quando os registros do cliente não aparecem imediatamente no Commerce headquarters.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: f1ad1f45abbc95cbf6d41b3c8681db781c6c9d23
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268829"
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
