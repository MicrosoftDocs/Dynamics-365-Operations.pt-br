---
title: (ER) Importar configurações de RCS
description: Este artigo fornece informações sobre como um usuário pode importar do RCS uma nova versão de configuração do ER.
author: kfend
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ''
ms.openlocfilehash: 55e7a3ae23b708acecb5ac219b885f43b4c7aa0a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290024"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) Importar configurações de RCS

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode importar uma nova versão de uma configuração de Relatório eletrônico (ER) do Regulatory Configuration Services (RCS) da Microsoft. Neste exemplo, você vai selecionar a versão da configuração de ER que foi definida em uma instância de RCS e importá-la para a instância atual da empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa porque as configurações de ER são compartilhadas entre empresas. Para concluir estas etapas, primeiro conclua as etapas do artigo, [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md). Para concluir essas etapas, você também deve ter acesso a uma instância de RCS que contenha pelo menos uma configuração de ER no status **Concluído** ou **Compartilhado**.

1. Acesse **Administração da organização** > **Espaços de trabalho** > **Relatório eletrônico**. 
2. Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**. Se você não visualizar esse provedor de configuração, conclua as etapas no artigo [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md). 
3. Se não tiver o ambiente do RCS provisionado para sua empresa, selecione o link externo **Regulatory services – Configuração** e siga as instruções para provisionar um ambiente do RCS. 
4. Selecione **Parâmetros de relatório eletrônico**. 
5. Selecione a guia **RCS**. 
6. Se o ambiente de RCS já tiver sido provisionado para sua empresa, use as URLs apresentadas na página para acessá-lo. 
7. Feche a página. 

## <a name="register-a-new-er-repository"></a>Registre um novo repositório de ER. 
1. Na lista, marque a linha selecionada. 
2. Selecione o provedor Litware, Inc. 
3. Selecione Repositórios. 
4. Selecione Adicionar para abrir a caixa de diálogo suspensa. 
5. No campo Tipo de repositório de configuração, insira 'RCS'. 
6. Selecione Criar repositório. 
7. No campo de nome de exibição do ambiente do RCS, insira ou selecione um valor. 
8. Selecione a instância de RCS desejada. Você pode ter várias delas. 
9. Selecione OK. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>Importe as configurações de ER do repositório com base em RCS
1. Selecione **Mostrar filtros**. 
2. Insira um valor de filtro de "RCS" no campo **Nome** usando o operador de filtro **começa com**. 
3. Ao abrir o repositório selecionado, na página **Conectar aos Regulatory Configuration Services**, escolha **Selecione aqui conectar-se aos Regulatory Configuration Services**. 
4. Selecione **Abrir**. 
5. Selecione **Fechar**. 
6. Selecione a versão desejada da configuração de ER e selecione **Importar** para exibi-la na instância atual.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
