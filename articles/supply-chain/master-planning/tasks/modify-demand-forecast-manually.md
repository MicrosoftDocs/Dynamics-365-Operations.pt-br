---
title: Modificar uma previsão de demanda manualmente
description: Este tópico descreve como alterar a previsão para um item
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889015"
---
# <a name="modify-a-demand-forecast-manually"></a>Modificar uma previsão de demanda manualmente

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como alterar a previsão para um item. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é criado para o planejador de produção.

## <a name="modify-the-forecast-for-a-selected-item"></a>Modifique a previsão para um item selecionado

Para modificar a previsão para um item selecionado:

1. Vá para **Módulos \> Gerenciamento de informações do produto \> Produtos \> Produtos lançados**.
1. Na lista, localize e selecione o registro desejado. Selecione o item cujo tipo deseja alterar a previsão.
1. No painel de ações, abra a guia **Planejar** e selecione **Previsão de demanda**.
1. Na lista, selecione uma linha. Se não houver linhas de previsão, crie uma nova linha selecionando **Novo** no painel de ação.  
1. No campo **Quantidade de vendas**, informe um número positivo. Este número representa a quantidade prevista para o item. Se você inserir um número negativo, será exibido um erro.
1. Preencha os outros campos, conforme necessário.
1. Selecione **Salvar** no painel de ações.

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a>Modifique a previsão para um ou mais itens no Microsoft Excel

Para modificar a previsão para um ou mais itens no Microsoft Excel:

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
