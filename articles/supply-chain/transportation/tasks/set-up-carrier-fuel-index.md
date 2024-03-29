---
title: Configurar um índice de combustível da transportadora
description: Este guia mostra como criar uma região do índice de combustível, um índice de combustível e um índice de combustível da transportadora.
author: Weijiesa
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb976369f9e8254f76a4de18df619d4420cf0538
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672672"
---
# <a name="set-up-a-carrier-fuel-index"></a>Configurar um índice de combustível da transportadora

[!include [banner](../../includes/banner.md)]

Este guia mostra como criar uma região do índice de combustível, um índice de combustível e um índice de combustível da transportadora. A região do índice de combustível especifica em qual região o índice de combustível deve ser aplicado, e o índice de combustível especifica um preço do combustível para um determinado período de tempo. Para refletir a alteração nos preços do combustível ao longo do tempo, você pode associar múltiplos índices de combustível da transportadora.  Essas tarefas são feitas tipicamente por um coordenador de transporte. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou usando seus próprios dados.


## <a name="create-a-fuel-index-region"></a>Crie uma região de índice de combustível
1. Acesse Gerenciamento de transporte > Configurar > Índices de combustível > Regiões de índices de combustível.
    * Primeiro você deve criar as diferentes regiões, onde você opera e calcula as diferentes sobretaxas de combustível.  
2. Clique em Novo.
3. No campo Região, digite um valor.
4. No campo Nome, digite um valor.
5. Clique em Salvar.

## <a name="create-a-fuel-index"></a>Crie um índice de combustível
1. Acesse Gerenciamento de transporte > Configurar > Índices de combustível > Índices de combustível.
    * Para as regiões que você configurou é preciso inserir os preços atuais do combustível.  
2. Clique em Novo.
3. No campo Região, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada.
5. No campo Preço por galão, insira um número.
6. No campo Data e hora efetiva de início, insira uma data e hora.
7. Clique em Salvar.

## <a name="create-a-carrier-fuel-index"></a>Crie um índice de combustível da transportadora
1. Acesse Gerenciamento de transporte > Configurar > Índices de combustível > Índices de combustível da transportadora.
2. Clique em Novo.
3. No campo Índice de combustível da transportadora, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Novo.
6. No campo Data e hora efetiva de início, insira uma data e hora.
7. No campo PPG De, insira um número.
    * Neste exemplo, você pode definir o campo PPG De para 1,95.  
8. No campo PPG Até, insira um número.
    * Neste exemplo, você pode definir o campo PPG Até para 2.  
9. No campo Porcentagem, insira um número.
    * Neste exemplo, você pode definir a porcentagem para 3.  
10. No campo Moeda, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize e selecione o PDV desejado.
12. Na lista, clique no link na linha selecionada.
13. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]