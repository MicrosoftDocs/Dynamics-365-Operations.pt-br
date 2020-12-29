---
title: Códigos de informação e grupos de códigos de informação
description: Este artigo oferece uma visão geral sobre códigos informativos, grupos de códigos informativos e como usá-los.
author: mugunthanm
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailInfocodeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 22761
ms.assetid: 99877dba-a6e3-4d88-ba0a-ee5913aea17e
ms.search.region: global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 046204d36e2fc7a69129aaf7fe027b2abc7e8dd9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410179"
---
# <a name="info-codes-and-info-code-groups"></a>Códigos de informação e grupos de códigos de informação

[!include [banner](includes/banner.md)]

Este artigo oferece uma visão geral sobre códigos informativos, grupos de códigos informativos e como usá-los.

Os códigos de informações fornecem uma maneira de capturar dados em um registro de ponto de venda (PDV). E possível usar códigos de informações para alertar o caixa a inserir informações durante várias ações no PDV, como vendas de item, devolução de itens ou seleção de clientes. Os caixas podem selecionar a entrada de uma lista ou inseri-la como um código, número, data ou texto. É possível atribuir códigos de informações a ações de loja predefinidas, a itens de varejo, a métodos de pagamento, a clientes ou a atividades específicas do ponto de venda. É possível usar os códigos de informações para fazer o seguinte:

- Capturar informações adicionais no momento da transação, como número do voo ou motivo de uma devolução.
- Solicitar ao caixa para selecionar preços de produtos específicos em uma lista.
- Vincular um subcódigo a um código de informações para solicitar que o caixa insira uma entrada ao executar uma atividade específica. Por exemplo, quando um cliente devolve um produto, é possível solicitar que o caixa pergunte porque o produto está sendo devolvido. Em seguida, será possível usar os subcódigos para exibir uma lista de motivos do qual o caixa pode selecionar.
- Vender um produto como uma venda normal, venda com desconto ou produto gratuito.
- Solicitar ao caixa para inserir um valor ou selecionar em uma lista de subcódigos quando a caixa registradora for aberta sem realizar uma operação de vendas.

## <a name="info-codes-group"></a>Grupo de códigos informativos

No Commerce, é possível criar grupos de códigos informativos. Os grupos de códigos de informações adicionam flexibilidade, permitindo a definição de códigos de informações e seu uso de maneiras mais versáteis. É possível usar grupos de códigos de informações das seguintes maneiras:

- Definir os códigos de informações e os reutilizar facilmente. Os códigos de informações incluídos em grupos de códigos de informações não têm dependência predefinida de outros códigos de informações. É possível incluir o mesmo código de informações em vários grupos de códigos de informações e usar a priorização para apresentar os mesmos códigos de informações na ordem em que fará sentido em qualquer situação específica.
- Vincular códigos de informações para outros códigos de informações ou grupos de códigos de informações para coletar informações sobre um produto ou uma transação, sem ter que definir um código separado de informações ou código de informações vinculado para cada cenário.

## <a name="info-code-examples"></a>Exemplos de códigos informativos

**Exemplo 1: Reutilizar códigos de informações**

É possível vincular códigos de informações de forma que, quando um código de informações for disparado, outro código de informações será disparado logo após ele. Por exemplo, ao vender determinados produtos, você pode solicitar que o caixa pergunte ao cliente se ele deseja comprar baterias e garantia do produto. Para outros produtos, você pode solicitar que o caixa pergunte ao cliente se ele deseja comprar baterias e coletar seu código postal. Se você criar códigos de informações vinculados para esses cenários, configure cada variação do código de informações de forma que seja solicitado ao caixa coletar as informações corretas. Se você usar grupos de códigos de informações, os códigos de informações comuns, como solicitar baterias, podem ser configurados uma vez e serem reutilizados em vários grupos de códigos de informações. Também é possível usar a priorização nos grupos de códigos de informações para identificar a ordem em que os avisos são exibidos.

**Exemplo 2: Vincular códigos de informações a grupos de códigos de informações**

Ao vender determinados produtos, como dispositivos móveis, você sempre deseja coletar um conjunto específico de informações, como número de telefone, identificador de equipamento móvel (MEID) e número de série. No entanto, você também deseja coletar informações diferentes de um tablet em relação a um telefone celular. É possível configurar um grupo de códigos de informações que inclui avisos sobre o número de telefone, o MEID e o número de série e vincular o grupo de códigos de informações ao código de informações individual. Quando o código de informações específico do produto é disparado, o grupo de códigos de informações pode ser disparado ao lado para permitir a coleta de dados comuns, sem a necessidade de definir vários conjuntos de códigos de informações vinculados para cada dispositivo.
