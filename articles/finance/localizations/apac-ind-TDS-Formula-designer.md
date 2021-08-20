---
title: Designer de fórmulas para cálculos de TDS
description: Este tópico fornece um exemplo de como o Imposto Deduzido na Origem (TDS) é calculado com base na fórmula definida para cada código de imposto TDS no grupo de TDS anexado à transação.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: e9c97982233b1f3dc3924fa42954b5cb8d09ffcaa07d19a3892b25737a6c29c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778860"
---
# <a name="formula-designer-for-tds-calculations"></a>Designer de fórmulas para cálculos de TDS

[!include [banner](../includes/banner.md)]

Este tópico fornece um exemplo de como o Imposto Deduzido na Origem (TDS) é calculado com base na fórmula definida para cada código de imposto TDS. Os códigos de imposto TDS são definidos no grupo de TDS anexado à transação. Antes de projetar fórmulas de TDS, conclua a configuração básica necessária para o TDS conforme listado nas etapas a seguir. 

- Configure grupos de componentes do TDS usando a página **Grupos de componentes de imposto retido na fonte**. 
- Configure os componentes do TDS e anexe o grupo de componentes do TDS aos componentes do TDS usando a página **Componentes de imposto retido na fonte**. 
- Configure os códigos de imposto TDS e anexe os componentes do TDS aos códigos de imposto usando a página **Códigos de impostos retidos na fonte**. 
- Configure grupos de imposto TDS usando a página **Grupos de imposto retido na fonte**. Em seguida, anexe os códigos de imposto TDS ao grupo de impostos e defina a fórmula, usando a página **Designer de fórmulas**. 

**Exemplo de fórmula**

Neste exemplo, o grupo de TDS, Aluguel, é anexado a uma fatura de compra criada para o fornecedor A. O valor da fatura é $ 100.000. Consulte a tabela a seguir para ver o cálculo do TDS para a fatura.

| Grupo de TDS                                                   | Códigos fiscais de TDS anexados ao grupo de TDS | Alíquota              | Base de tributação (designer de fórmulas) | Expressão de cálculo (designer de fórmulas) | Valor base | Valor calculado de TDS |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| Aluguel                                                         | TDS (componente de TDS-TDS)                | 10%                | Valor bruto                      |                                            | 100,000      | 10,000                 |
| Sobretaxa (componente de TDS-sobretaxa)                         | 10%                                     | Valor bruto excluído | +TDS                              |                   10000                    | 1.000        |                       |
| PE-Cess (componente de TDS-PE-Cess)                            | 2%                                      | Valor bruto excluído | +TDS+Sobretaxa                    |                   11000                    | 220         |                       |
| SHE Cess (componente de TDS-SHE Cess)                          | 1%                                      | Valor bruto excluído | +TDS+Sobretaxa                    |                   11000                    | 110         |                       |
| **Total** **TDS**  **calculado** **para** **a** **fatura** | **11,330**                               |                    |                                   |                                            |             |                       |

As entradas de comprovante são criadas da seguinte forma.

| Conta           | Débito  | Crédito |
| ----------------- | ------ | ------ |
| Aluguel              | 100,000 |        |
| Fornecedor A          |        | 100,000 |
| Fornecedor A          | 11,330  |        |
| TDS a pagar       |        | 10,000  |
| Sobretaxa a pagar |        | 1.000   |
| PE-Cess a pagar   |        | 220    |
| SHE Cess a pagar  |        | 110    |
