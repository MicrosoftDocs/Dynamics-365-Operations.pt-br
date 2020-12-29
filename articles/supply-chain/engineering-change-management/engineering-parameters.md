---
title: Parâmetros do gerenciamento de alteração de engenharia
description: Este tópico explica como configurar recursos de gerenciamento de alterações de engenharia do Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 0cf0e56a8aece98379aa0f181d7b7ff665767544
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4422636"
---
# <a name="engineering-change-management-parameters"></a>Parâmetros do gerenciamento de alteração de engenharia

[!include [banner](../includes/banner.md)]

A página **Parâmetros de gerenciamento de alterações de engenharia** contém parâmetros de configuração que alteram o comportamento padrão relacionado à estrutura de produtos de lançamento e aos processos de gerenciamento de alterações de engenharia.

## <a name="open-the-engineering-change-management-parameters-page"></a>Abrir a página Parâmetros de gerenciamento de alterações de engenharia

Para abrir a página **Parâmetros de gerenciamento de alterações de engenharia**, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Parâmetros de gerenciamento de alterações de engenharia**. Você pode definir os campos conforme descrito nas seções restantes deste tópico.

## <a name="release-control-tab"></a>Guia Controle de versão

A tabela a seguir descreve os campos disponíveis na guia **Controle de versão** da página **Parâmetros de gerenciamento de alterações de engenharia**. Esses campos afetam o processo de estrutura de produtos de lançamento.

| Campo | descrição |
|---|---|
| Regra de número de item | Selecione como o número do item deve ser definido quando o produto é liberado para uma entidade legal. Selecione *Número do produto de engenharia* se o número do produto na entidade legal de recebimento corresponder ao número do produto na empresa de engenharia. Selecione *Sequência numérica do item local* se o produto assumir o próximo número na sequência numérica dos números de produto na entidade legal de recebimento. |
| Regra de nome da BOM | Selecione como o nome da BOM (lista de materiais) é definido quando o produto é recebido (liberado) em uma entidade legal. Selecione *Nome da engenharia* ou *Número do item de recebimento*. |
| Regra de nome de roteiro | Selecione como o nome de rota deve ser definido quando a rota de um produto é recebida (liberada) em uma entidade legal. Selecione *Nome da engenharia* ou *Número do item de recebimento*. |
| Executar verificação da BOM | Selecione se uma verificação de BOM será executada quando o produto for recebido (liberado) em uma entidade legal. |
| Comportamento de liberação da BOM inativa | Selecione se um produto poderá ser liberado se tiver uma BOM inativa. Selecione *Aceitar*, *Apenas aviso* ou *Não permitido*. |
| Comportamento de liberação de roteiro inativo | Selecione se um produto poderá ser liberado se tiver uma rota inativa. Selecione *Aceitar*, *Apenas aviso* ou *Não permitido*.|
| Aceitação do produto | Selecione se uma etapa adicional para aceitação é necessária para que o produto possa ser liberado na entidade legal. Selecione *Manual* para adicionar a etapa de aceitação. Neste caso, a página **Versões de produtos em aberto** mostrará os produtos. Selecione *Automático* para mostrar o produto diretamente na página **Produtos liberados** na entidade legal de destino logo após o produto ser liberado junto com a estrutura de produtos de lançamento. |

## <a name="engineering-change-management-tab"></a>Guia Gerenciamento de alterações de engenharia

A tabela a seguir descreve os campos disponíveis na guia **Gerenciamento de alterações de engenharia** da página **Parâmetros de gerenciamento de alterações de engenharia**. Essas configurações afetam o processo de gerenciamento de alterações de engenharia.

| Campo | descrição |
|---|---|
| Categoria | A categoria padrão que será usada quando uma solicitação de alteração de engenharia for criada. |
| Prioridade | A prioridade padrão que será usada quando uma solicitação de alteração de engenharia for criada. |
| Regra de severidade | Selecione como a gravidade de uma ordem de alteração de engenharia deve ser estabelecida. Selecione *Manual* se for esperado que o usuário insira um valor no campo **Gravidade**. Selecione *Calcular* para que o sistema calcule o valor do campo **Gravidade** ao selecionar **Calcular gravidade** no Painel de Ações da ordem de alteração de engenharia. Nesse caso, o sistema usará as regras de gravidade definidas na página **Conjunto de regras de gravidade**. Selecione *Calcular automaticamente* para que o valor do campo **Gravidade** seja calculado automaticamente e preenchido de acordo com os conjuntos de regras de gravidade. |
| Lançar produtos afetados novamente | Este campo é aplicável quando você libera de novo produtos por meio de uma ordem de alteração de engenharia. Você pode selecionar se todos os produtos ou somente os produtos afetados devem ser propostos na caixa de diálogo **Liberações**. |
| Níveis da BOM a liberar | A profundidade do nível de BOM a ser liberado. Se a BOM tiver mais níveis (ou seja, se for mais profunda) que o valor especificado aqui, somente os níveis até o valor especificado serão liberados. |
