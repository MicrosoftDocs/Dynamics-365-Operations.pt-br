---
title: Gerar relatórios adicionando conteúdo como XML bruto
description: Você pode criar os formatos de relatórios eletrônicos (ER) que geram de documentos de saída no formato XML.
author: kfend
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: 87b70d5893d71e5022205a2f39f8263edf6d5280
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277532"
---
# <a name="generate-reports-by-adding-content-as-raw-xml"></a>Gerar relatórios adicionando conteúdo como XML bruto

[!include[banner](../includes/banner.md)]

Você pode usar o novo elemento de formato **XML BRUTO** para criar formatos os relatórios de eletrônicos (ER) que geram documentos de saída no formato XML. Em alguns casos, talvez pode prefira adicionar dados XML brutos para esses relatórios por um ou mais destes motivos:

- É mais conveniente usar o XML bruto para o projeto original e a manutenção em andamento de um relatório porque a estrutura XML pode ser gerada automaticamente executando uma expressão de tempo de execução. Portanto, várias associações não precisam ser determinadas para vários elementos do formato em tempo de design. Isso é possível quando as fontes de dados que você estiver usando contiverem informações que podem ser usadas para criar elementos XML quando o relatório for gerado.
- Nenhum outro método pode ser usado para preencher o relatório com o conteúdo XML que já foi recebido e armazenado no sistema. Por exemplo, a resposta XML que é gerada talvez precise conter o conteúdo de uma solicitação XML que foi enviada anteriormente.
- Nenhum outro método pode ser usado para inserir caracteres no documento gerado com base nos códigos numéricos. Para alguns idiomas e caracteres, os códigos desse tipo não existem. Os exemplos incluem a letra grega rho (ρ) e os códigos da entidade HTML, como por exemplo, \&eacute; para um *e* que tenha um acento agudo (é).

> [!NOTE]
> Saiba que a estrutura não é controlada se o conteúdo XML colocado para o documento gerado usando o elemento do formato **RAW XML** estiver correto.

Para saber mais sobre este recurso, execute os guias de tarefas **ER - Usar dados XML brutos para gerar relatórios XML (Parte 1: Criar modelo de dados)** e **ER - Usar dados XML brutos para gerar relatórios XML (Parte 2: Criar e executar relatório)** que fazem parte do processo empresarial **7.5.4.3 Adquirir/Desenvolver componentes de serviço/solução de TI (10677)** e podem ser baixadas no [Centro de Download da Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Esses guias de tarefas o conduzem pelo processo de configuração de um formato de ER para inserir dados de XML brutos em arquivos gerados.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
