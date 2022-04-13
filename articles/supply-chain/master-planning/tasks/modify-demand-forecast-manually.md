---
title: 'Guia: Modificar uma previsão de demanda manualmente'
description: Este tópico descreve como alterar a previsão para um item
author: t-benebo
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e5030bf97bee8dc475f22473ecc87e900298b6f
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469358"
---
# <a name="guide-modify-a-demand-forecast-manually"></a>Guia: Modificar uma previsão de demanda manualmente

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como alterar a previsão para um item. Esse procedimento é criado para o planejador de produção.

## <a name="modify-the-forecast-for-a-selected-item"></a>Modifique a previsão para um item selecionado

Para modificar a previsão para um item selecionado:

1. Acesse **Módulos \> Gerenciamento de informações do produto \> Produtos \> Produtos lançados**.
1. Na lista, localize e selecione o registro desejado. Selecione o item cujo tipo deseja alterar a previsão.
1. No painel de ações, abra a guia **Planejar** e selecione **Previsão de demanda**.
1. Na lista, selecione uma linha. Se não houver linhas de previsão, crie uma nova linha selecionando **Novo** no painel de ação.  
1. No campo **Quantidade de vendas**, informe um número positivo. Este número representa a quantidade prevista para o item. Se você inserir um número negativo, será exibido um erro.
1. Preencha os outros campos, conforme necessário.
1. Selecione **Salvar** no painel de ações.

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a>Modificar a previsão para um ou mais itens com o Microsoft Excel

Como modificar a previsão para um ou mais itens com o Microsoft Excel:

1. Execute um destes procedimentos:
    - Abra a página **Previsão de demanda** de um item (pode ser qualquer um) conforme descrito na seção anterior.
    - Acesse **Planejamento mestre \> Previsão \> Entrada de previsão manual \> Linhas de previsão de demanda**.
1. No painel de ações, abra a guia **Abrir no Microsoft Office \> Entradas da previsão de demanda**.
1. Selecione um local para fazer download, salve e abra o arquivo baixado no Excel.
1. Se você vir um aviso, selecione a opção **Habilitar edição**.
1. No Excel, entre no Supply Chain Management usando o painel de tarefas do Microsoft Dynamics. Você deve conectar-se com a opção **Continuar conectado** habilitada e deve confiar no aplicativo de conexão de dados.
1. A planilha do Excel agora mostra todas as linhas de previsão de demanda atuais da sua empresa.  Adicione, apague e edite as linhas de previsão de demanda, conforme necessário.
1. Selecione **Publicar** no painel da tarefas do Microsoft Dynamics para fazer o upload de suas alterações no Supply Chain Management.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
