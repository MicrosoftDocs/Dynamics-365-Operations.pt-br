---
title: Fazer check-in para o módulo de retirada
description: Este artigo descreve o check-in do módulo de retirada e explica como configurá-lo no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 7002db893da1802063148a9b800ffa92f3e5f065
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885466"
---
# <a name="check-in-for-pickup-module"></a>Fazer check-in para o módulo de retirada

[!include [banner](includes/banner.md)]

Este artigo descreve o check-in do módulo de retirada e explica como configurá-lo no Microsoft Dynamics 365 Commerce.

O check-in do módulo de retirada fornece uma página de confirmação para clientes que usam os recursos de check-in do cliente do Dynamics 365 Commerce para notificar uma loja sobre a chegada. O check-in do módulo de retirada também permite configurar um formulário que coleta informações adicionais de clientes para facilitar a entrega da ordem. Essas informações incluem o número de spot de estacionamento de um cliente e a marca e o modelo de seu veículo. 

## <a name="module-properties"></a>Propriedades do módulo

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Texto de confirmação | Cadeia de caracteres de texto | Conteúdo do título que aparece na página de confirmação de check-in. |
| Mostrar código QR | **Verdadeiro** ou **Falso** | Quando essa propriedade é definida como **Verdadeira**, a página de confirmação de check-in mostra um código QR que representa a ID de confirmação da ordem. |
| Título de informações adicionais | Cadeia de caracteres de texto | Conteúdo do título exibido quando são configurados campos de informações adicionais. |
| Chaves de informações adicionais | Par ID do recurso/valor do recurso | Cada chave cria um campo de formulário e uma etiqueta associada que são usados para coletar informações adicionais dos clientes. |
| Chaves de informações adicionais \> ID do recurso | Cadeia de caracteres de texto | Cada chave de informações cria um campo de formulário e uma etiqueta associada que são usados para coletar informações adicionais dos clientes. Esta propriedade identifica a chave de informações adicional. Na tarefa criada no PDV (ponto de venda), o valor dessa propriedade é mostrado como o rótulo no campo instruções. |
| Chaves de informações adicionais \> Valor do recurso | Cadeia de caracteres de texto | A etiqueta do campo de texto da tarefa no PDV. |
| Chaves de informações adicionais \> Obrigatórias | **Verdadeiro** ou **Falso** | Esta propriedade especifica se os clientes devem preencher o campo do formulário antes de continuar. Quando essa propriedade é definida como **Verdadeira**, um asterisco é renderizado próximo ao rótulo do formulário e uma verificação nula é feita para evitar que os clientes continuem, se nenhum valor for inserido. |

## <a name="add-the-check-in-for-pickup-module-to-a-page"></a>Adicionar o check-in para o módulo de retirada a uma página

O check-in para o módulo de retirada deve ser adicionado à nova página criada para confirmação de check-in. Essa página servirá como a experiência de confirmação de check-in para clientes que selecionam o link **Estou aqui** ou o botão no seu email. 

## <a name="configure-the-additional-information-form"></a>Configure o formulário Informações adicionais

Por padrão, se nenhuma chave de informação adicional estiver configurada, o módulo mostrará aos clientes a página de confirmação de check-in. Como a confirmação de check-in é exibida, uma tarefa é criada no PDV para a loja na qual a ordem é retirada.

Quando uma ou mais chaves de informações adicionais são configuradas, é solicitado que os clientes primeiro insiram informações. Quando eles selecionam **Enviar**, a confirmação de check-in é mostrada e uma tarefa é criada no PDV. 

## <a name="additional-resources"></a>Recursos adicionais

[Habilitar notificações de check-in do cliente no ponto de venda (PDV)](enable-customer-check-in.md)
