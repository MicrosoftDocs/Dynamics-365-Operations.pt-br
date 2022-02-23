---
title: Definir dimensões financeiras
description: Este guia de tarefas demonstra como adicionar uma dimensão financeira apoiada por entidade e dimensão financeira personalizada.
author: aprilolson
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6fbe739eec0cfa1e7b0276872640bd4f82be3ef7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440181"
---
# <a name="define-financial-dimensions"></a>Definir dimensões financeiras

[!include [banner](../../includes/banner.md)]

Este guia de tarefas demonstra como adicionar uma dimensão financeira apoiada por entidade e dimensão financeira personalizada.  Este guia usa a empresa de dados de demonstração USMF.


## <a name="create-an-entity-backed-financial-dimension"></a>Criar uma dimensão financeira apoiada por entidade
1. Vá para **Painel de navegação > Módulos > Contabilidade > Plano de contas > Dimensões > Dimensões financeiras**.
2. Clique em **Novo**.
3. No campo **Usar valores de**, selecione uma entidade definida pelo sistema para basear a dimensão financeira. 
4. No campo **Nome de dimensão**, digite um valor para descrever a dimensão financeira. O nome pode ser diferente da entidade definida pelo sistema, mas não pode conter espaços ou caracteres especiais.
5. Clique em **Ativar**. A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas. Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser usada até ser ativada.  
6. Clique em **Fechar** na mensagem de ativação.
7. Clique em **Ativar**. A ativação da dimensão pode ser programada para execução por lote em data e horário específicos.  
8. No **Painel de Ação**, clique em **Valores de dimensão**. Alguns valores de dimensão são específicos da companhia. Você pode verificar se eles são específicos da companhia se o nome da companhia estiver sendo mostrado na lista de valores de dimensão.  

## <a name="create-a-custom-financial-dimension"></a>Criar uma dimensão financeira personalizada
1. Feche a página.
2. Clique em **Novo**.
3. No campo **Usar valores de**, selecione **Dimensão personalizada**.
4. No campo **Nome de dimensão**, digite um valor para descrever a dimensão financeira.
    - O nome não pode conter espaços ou caracteres especiais.  
    - Você também pode especificar uma máscara de conta para limitar o valor e o tipo de informação que é possível inserir para valores de dimensão.   
    - Você pode inserir os caracteres que permanecem iguais para cada valor de dimensão, como letras ou um hífen. Você também pode inserir sinais numéricos (#) e o e comercial (&) como espaços reservados para as letras e números que mudarão sempre que um valor de dimensão for criado. Use um sinal numérico (#) como um espaço reservado para um número e um e comercial (&) como um espaço reservado para uma letra.  Exemplo: para limitar o valor de dimensão às letras CC e a três números, insira CC-### como a máscara de formato.  
5. Clique em **Ativar**. A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas. Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser usada até ser ativada.     
6. Clique em **Ativar**. A ativação da dimensão pode ser programada para execução por lote em data e horário específicos.      
7. No **Painel de Ação**, clique em **Valores de dimensão**.
8. Clique em **Novo**.
9. No campo **Valor da dimensão**, digite um nome para descrever o valor da dimensão financeira.
10. No campo **Descrição**, digite uma descrição que defina seu valor de dimensão financeira.

