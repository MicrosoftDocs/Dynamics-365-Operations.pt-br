---
title: Definir dimensões financeiras
description: Este procedimento mostra como adicionar uma dimensão financeira apoiada por entidade e dimensão financeira personalizada.
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10a991938f68c0ade19999e48a02f032c92a6779
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716933"
---
# <a name="define-financial-dimensions"></a>Definir dimensões financeiras

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como adicionar uma dimensão financeira apoiada por entidade e dimensão financeira personalizada. Este guia usa a empresa de dados de demonstração USMF.

## <a name="create-an-entity-backed-financial-dimension"></a>Criar uma dimensão financeira apoiada por entidade
1. Acesse **Painel de navegação > Módulos > Contabilidade > Plano de contas > Dimensões > Dimensões financeiras**.
2. Clique em **Novo**.
3. No campo **Usar valores de**, selecione uma entidade definida pelo sistema para basear a dimensão financeira. 
4. No campo **Nome de dimensão**, digite um valor para descrever a dimensão financeira. O nome pode ser diferente da entidade definida pelo sistema, mas não pode conter espaços ou caracteres especiais.
5. Clique em **Ativar**. A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas. Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser usada até ser ativada.  
6. Clique em **Fechar** na mensagem de ativação.
7. Clique em **Ativar**. A ativação da dimensão pode ser programada para execução por lote em data e horário específicos.  
8. No **Painel de Ação**, clique em **Valores de dimensão**. Alguns valores de dimensão são específicos da companhia. Você pode verificar se eles são específicos da companhia se o nome da companhia estiver sendo mostrado na lista de valores de dimensão.  

## <a name="create-a-custom-financial-dimension"></a>Criar uma dimensão financeira personalizada
1. Clique em **Novo**.
2. No campo **Usar valores de**, selecione **Dimensão personalizada**.
3. No campo **Nome de dimensão**, digite um valor para descrever a dimensão financeira.
    - O nome não pode conter espaços ou caracteres especiais.  
    - Você também pode especificar uma máscara de conta para limitar o valor e o tipo de informação que é possível inserir para valores de dimensão.   
    - Você pode inserir os caracteres que permanecem iguais para cada valor de dimensão, como letras ou um hífen. Você também pode inserir sinais numéricos (#) e o e comercial (&) como espaços reservados para as letras e números que mudarão sempre que um valor de dimensão for criado. Use um sinal numérico (#) como um espaço reservado para um número e um e comercial (&) como um espaço reservado para uma letra.  Exemplo: para limitar o valor de dimensão às letras CC e a três números, insira CC-### como a máscara de formato.  
4. Clique em **Ativar**. A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas. Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser usada até ser ativada.     
5. Clique em **Ativar**. A ativação da dimensão pode ser programada para execução por lote em data e horário específicos.      
6. No **Painel de Ação**, clique em **Valores de dimensão**.
7. Clique em **Novo**.
8. No campo **Valor da dimensão**, digite um nome para descrever o valor da dimensão financeira.
9. No campo **Descrição**, digite uma descrição que defina seu valor de dimensão financeira.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
