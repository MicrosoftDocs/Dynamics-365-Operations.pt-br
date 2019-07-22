---
title: (ER) Importar configurações de RCS
description: Este tópico fornece informações sobre como um usuário pode importar uma nova versão de configuração de ER de RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c458cf815837fb7e4688c4c0443b7962cac403a5
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/04/2019
ms.locfileid: "1726997"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) Importar configurações de RCS

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode importar uma nova versão de uma configuração de Relatório eletrônico (ER) do Regulatory Configuration Services (RCS) da Microsoft. Neste exemplo, você selecionará a versão da configuração de ER que foi configurada na instância de RCS e importá-la para a instância do Finance and Operations atual para a empresa exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa porque as configurações de ER são compartilhadas entre empresas. Para concluir estas etapas, primeiro é necessário concluir as etapas do tópico, [Criar um provedor de configuração e marcá-lo como ativo](er-configuration-provider-mark-it-active-2016-11.md). Para concluir essas etapas, você também deve ter acesso a uma instância de RCS que contenha pelo menos uma configuração de ER no status **Concluído** ou **Compartilhado**.

1. Vá para **Administração da organização** > **Espaços de trabalho** > **Relatório eletrônico**. 
2. Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**. Caso não veja este provedor de configuração, conclua as etapas do tópico, [Criar um provedor de configuração e marcá-lo como ativo](er-configuration-provider-mark-it-active-2016-11.md). 
3. Se não tiver o ambiente do RCS provisionado para sua empresa, clique no link externo **Regulatory services – Configuração** e siga as instruções para provisionar um ambiente do RCS. 
4. Clique em **Parâmetros de relatório eletrônico**. 
5. Clique na guia **RCS**. 
6. Se o ambiente de RCS já tiver sido provisionado para sua empresa, use as URLs apresentadas na página para acessá-lo. 
7. Feche a página. 

## <a name="register-a-new-er-repository"></a>Registre um novo repositório de ER. 
1. Na lista, marque a linha selecionada. 
2. Selecione o provedor Litware, Inc. 
3. Clique em Repositórios. 
4. Clique em Adicionar para abrir a caixa de diálogo suspensa. 
5. No campo Tipo de repositório de configuração, insira 'RCS'. 
6. Clique em Criar repositório. 
7. No campo de nome de exibição do ambiente do RCS, insira ou selecione um valor. 
8. Selecione a instância de RCS desejada. Observe que você pode ter várias delas. 
9. Clique em OK. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>Importe as configurações de ER do repositório com base em RCS
1. Clique em **Mostrar filtros**. 
2. Insira um valor de filtro de "RCS" no campo **Nome** usando o operador de filtro **começa com**. 
3. Ao abrir o repositório selecionado, na página **Conectar aos Regulatory Configuration Services**, clique no link **Clique aqui para conectar-se aos Regulatory Configuration Services**. 
4. Clique em **Abrir**. 
5. Clique em **Fechar**. 
6. Selecione a versão desejada da configuração de ER e clique em **Importar** para exibi-la na instância do Finance and Operations atual.

