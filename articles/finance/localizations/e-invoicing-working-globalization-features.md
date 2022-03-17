---
title: Componentes de recurso de globalização
description: Este tópico oferece uma visão geral dos componentes de recurso de globalização.
author: dkalyuzh
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 87d7dd231b9ccda7761c91f129659c18039f3299
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371526"
---
# <a name="globalization-feature-components"></a>Componentes de recurso de globalização

[!include [banner](../includes/banner.md)]

Um recurso de globalização é um conjunto de componentes que define as regras para a transformação de dados em configurações de relatório eletrônico (ER). Esses componentes incluem instruções para o processamento de documentos eletrônicos e o envio ou recebimento deles de canais externos. Eles também incluem condições que definem quando um recurso deve ser executado para os dados comerciais recebidos.

Todos os componentes dependem uns dos outros. Os recursos de globalização facilitam a criação e a manutenção dessa dependência, bem como o gerenciamento do ciclo de vida e a versão do conjunto de componentes.

## <a name="access-electronic-invoicing-feature-components"></a>Acessar componentes de recurso do Faturamento eletrônico 

1. Entre na conta RCS (serviço de configuração regulatória).
2. No espaço de trabalho **Recurso de globalização** na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.

    Os recursos de globalização têm vários componentes. A página **Recursos de faturamento eletrônico** inclui uma guia separada para cada componente.

    - **Versão** – Este componente oferece suporte ao gerenciamento do ciclo de vida do recurso. Você pode usá-lo para gerenciar o status de versões diferentes do recurso.
    - **Configurações** – Este componente permite que você gerencie, exiba e edite configurações de mapeamento de formato e formatação de ER usadas no pipeline de processamento.
    - **Configurações** – esse componente permite que os usuários dos Serviços de globalização, como um serviço de faturamento eletrônica, gerenciem a configuração da versão do recurso relacionado. Portanto, ele oferece suporte à construção flexível de regras de comunicação e respostas.
    - **Ambientes** – Esse componente permite que os usuários dos serviços de globalização, como um serviço de faturamento eletrônico, gerenciem o ambiente no qual a configuração da versão do recurso é usada. Ele também permite conceder autorização aos usuários que terão acesso à configuração da versão do recurso.
    - **Organizações** – Esse componente permite que os usuários compartilhem o recurso com organizações externas.
    - **Marcas** – Esse componente permite marcar recursos que podem ser usados no gráfico de globalização para a referência.
