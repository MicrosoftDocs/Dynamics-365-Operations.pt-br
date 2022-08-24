---
title: Trabalhar com configurações
description: Este artigo fornece uma visão geral do cenário principal para trabalhar com configurações de relatório eletrônico (ER) do espaço de trabalho Recursos de globalização.
author: gionoder
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: d87559405d2490c314eb2c8b88268af0dc0dfaca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283045"
---
# <a name="work-with-configurations"></a>Trabalhar com configurações

[!include [banner](../includes/banner.md)]

As configurações de relatório eletrônico (ER) são um dos conjuntos principais de componentes dos recursos de faturamento eletrônico. Uma configuração de ER contém a configuração da estrutura de arquivos e um conjunto de regras de transformação para transformar dados de duas maneiras:

- **Exportar configuração de formato de ER** – Essa configuração transforma dados da estrutura interna unificada (modelo de ER) no formato de arquivo eletrônico.
- **Importar configuração de formato de ER** – Essa configuração transforma dados do formato de arquivo eletrônico na estrutura interna unificada (modelo de ER).

Além de gerar arquivos eletrônicos de saída no formato predefinido, as configurações de ER são amplamente usadas para analisar mensagens de entrada de serviços Web externos como respostas. Essa funcionalidade ajuda a criar lógica configurável para obter os resultados da comunicação com canais externos, converter esses resultados (códigos, mensagens e logs) na estrutura legível pelo usuário e, depois, passar essas informações para o aplicativo cliente.

Para começar a usar as configurações de ER no seu recurso de faturamento eletrônico, você deve vinculá-las ao recurso e torná-las disponíveis na guia **Configurações** da versão do recurso atual. Você pode trabalhar com uma configuração vinculada de ER selecionando **Adicionar**, **Excluir**, **Editar** ou **Exibir**.

Para poder adicionar um link a uma configuração ER, a configuração deve existir no repositório do RCS (Regulatory Configuration Service). Para revisar as configurações de ER disponíveis no seu repositório do RCS, siga estas etapas.

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Relatório eletrônico**, na seção **Configurações**, selecione o bloco **Configurações de relatórios**.

Para obter informações sobre como criar uma nova configuração ER ou importar uma configuração de ER existente do repositório global, consulte [Relatório eletrônico](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Para ajustar uma configuração vinculada de ER, selecione **Editar** na guia **Configurações** do recurso de faturamento eletrônico atual. O sistema cria automaticamente uma versão da configuração de ER. Se a versão atual não foi criada pelo provedor de configuração ativo, o sistema cria uma versão derivada que usa o provedor de configuração. Se a versão atual tiver sido criada pelo provedor de configuração ativo, o sistema criará uma nova versão. Em ambos os casos, você pode modificar a versão criada e executar automaticamente todas as atualizações necessárias.
