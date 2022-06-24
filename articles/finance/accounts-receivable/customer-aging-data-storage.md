---
title: Armazenamento dos dados de classificação por vencimento do cliente
description: Este artigo descreve o processo de uso do armazenamento externo para dados de classificação por vencimento do cliente. Você pode executar o processo de armazenamento de dados de classificação por vencimento do Cliente para disponibilizar a saída para exportação para um sistema externo.
author: JodiChristiansen
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d7a66485cc9a538f5c3999009b6dbe295d7a5b9f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894132"
---
# <a name="customer-aging-data-storage"></a>Armazenamento dos dados de classificação por vencimento do cliente

[!include [banner](../includes/banner.md)]

Este artigo descreve o processo de uso do armazenamento externo para dados de classificação por vencimento do cliente. Na Microsoft Dynamics 365 Finance, você pode executar o processo de **armazenamento de dados de classificação por vencimento do Cliente** para disponibilizar a saída para exportação para um sistema externo. Quando você executa o processo, as mesmas opções de relatório de classificação por vencimento disponíveis no sistema estarão disponíveis para os sistemas externos. Os detalhes sempre são incluídos nos dados exportados.

Pode ser útil disponibilizar os dados de classificação por vencimento do cliente para um sistema externo para armazenamento em casos nos quais a saída contém muitos clientes e/ou várias transações. Se o relatório existente de **Classificação por vencimento do Cliente** expirar porque há muitos dados a serem impressos, esse recurso oferecerá uma forma alternativa de obter os mesmos dados.

## <a name="enable-the-customer-aging-data-storage-feature"></a>Habilitar o recurso de armazenamento de dados de classificação por vencimento do Cliente

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de gerenciamento de recursos para verificar o status do recurso e habilitá-lo, se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** Crédito e cobranças
- **Nome do recurso:** armazenamento de dados de classificação por vencimento do Cliente

## <a name="run-the-customer-aging-data-storage-process"></a>Executar o processo de armazenamento de dados de classificação por vencimento do Cliente

1. Acesse **Crédito e cobranças \> Consultas e relatórios \> Pagamentos \> Armazenamento de dados de classificação por vencimento do Cliente**.
2. Selecione **Novo**.
3. No campo **Nome**, digite um nome para o processo.
4. Defina os parâmetros restantes conforme necessário.

    > [!NOTE]
    > Os detalhes da transação sempre são incluídos, e o processamento é sempre feito em um trabalho em lotes.

5. Selecione **OK**.
6. Atualize a página de **armazenamento de dados de classificação por vencimento do Cliente** para ver os valores de **Nome do lote** e **Tempo de execução do lote** que são mostrados juntamente com o valor do **Status de processamento**. Quando o trabalho em lotes é concluído, o campo **Status do processamento** é definido como **Concluído** e o campo **Número de linhas de classificação por vencimento** é definido. Se o trabalho em lotes for recorrente, o campo **Status do processamento** será definido como **Em espera**.
7. Selecione o botão **Filtro** ao lado do campo **Número de linhas de classificação por vencimento** para revisar os filtros que foram adicionados para o trabalho em lotes.

A página de **armazenamento de dados de classificação por vencimento do Cliente** não inclui os resultados. No entanto, a entidade de dados de **armazenamento de dados de classificação por vencimento do Cliente** permite exportar a saída para qualquer formato compatível com o Gerenciamento de dados.

> [!NOTE]
> Antes de exportar, adicione um filtro para limitar os resultados exportados à classificação por vencimento mais recente. Por exemplo, adicione os seguintes critérios para retornar a execução do lote mais recente:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchName())
>
> Opcionalmente, adicione os seguintes critérios para retornar a execução do lote mais recente para o usuário atual:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchNameForCurrentUser())
