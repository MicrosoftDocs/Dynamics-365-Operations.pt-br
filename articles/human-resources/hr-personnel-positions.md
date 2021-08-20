---
title: Posições
description: Este tópico descreve os elementos conceituais que um cargo pode incluir. Ele também fornece exemplos que mostram como você pode usar esses elementos na sua organização.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: anbichse
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 269054
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c8311df31326faeadd280585115338317b19125d54f3a526b4ccc6ef6684ad2c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754743"
---
# <a name="positions"></a>Posições

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve os elementos conceituais que um cargo pode incluir. Ele também fornece exemplos que mostram como você pode usar esses elementos na sua organização.

Para poder criar uma posição, um trabalho deve ser configurado. Alguns detalhes de cargo, como a região de remuneração, a atribuição do trabalhador, a duração do cargo e a relação organizacional, são de data efetiva.

## <a name="general-information"></a>Informações gerais

Ao criar um cargo, você deve selecionar um trabalho. As seguintes informações serão preenchidas automaticamente a partir do trabalho selecionado:

- descrição
- Cargo
- Equivalente ao horário integral
- Família do trabalho

O título do cargo é usado para fazer referência ao cargo de um funcionário. (O título listado no funcionário não é usado). Portanto, os títulos de cargo devem ser padronizados o máximo possível.

> [!NOTE]
> Um trabalhador não pode ser atribuído a um cargo em uma data anterior à data disponível para atribuição.
>
> Um parâmetro na guia **Cargos** da página **Parâmetros compartilhados de recursos humanos** controla o comportamento de atribuição do trabalhador. Selecione um dos seguintes valores:
>
> - **Sempre** – Você pode atribuir trabalhadores a novas posições quando estas forem criadas. Quando as posições são criadas, a data e hora **Disponível para a atribuição** na guia **Geral** da página **Posição** são automaticamente definidas para a data e hora de criação.
> - **Nunca** – Você não pode atribuir trabalhadores a novas posições quando estas forem criadas. Se você selecionar esta opção, deverá abrir a página **Cargo** para cada novo cargo quando ele for disponibilizado. Em seguida, na guia **Geral**, insira a data **Disponível para atribuição** a fim de habilitar a atribuição de trabalhador. Se você selecionar esta opção, a data de atribuição do trabalhador será definida como **Nunca** por padrão quando você tentar atribuir o trabalhador.

## <a name="position-duration"></a>Duração da posição

Todas os cargos entram em vigor por um período específico referido como duração. Por exemplo, os cargos de férias podem ter a duração de 1º de maio de 2021 até 31 de agosto de 2021. A data de ativação é a data em que o cargo está ativo no sistema. A data de desativação é a data em que o cargo não está mais ativo no sistema.

Lembre-se de que a data disponível para atribuição nem a data de atribuição do trabalhador podem ser anteriores à data de ativação. Um cargo não é considerado ativo até que a data de ativação seja atingida. Além disso, uma atribuição de trabalhador não pode ultrapassar a data de desativação do cargo.

## <a name="reports-to-position"></a>Cargo Subordinado de

Os cargos são elementos importantes no nível inferior de uma hierarquia organizacional. Na página **Cargo**, você pode especificar o cargo ao qual um cargo é subordinado. Quando você atribui um trabalhador a um cargo que está subordinado a outro cargo, você cria uma relação de subordinação entre os trabalhadores atribuídos a esses dois cargos. Por exemplo, o cargo 000220 responde ao cargo 000300. Kim Akers está atribuído ao cargo 000220, e Sanjay Patel está atribuído ao cargo 000300. Portanto, Kim Akers responde a Sanjay Patel.

> [!TIP]
> O cargo de supervisor é usado em todo o sistema para determinar quem é o gerente de um funcionário. No exemplo anterior, se a função de gerente for atribuída a Sanjay Patel no sistema, ele verá Kim Akers como um subordinado direto no Autoatendimento do Gerente. A relação de subordinação também pode ser usada ao criar regras de roteiro de fluxo de trabalho e tarefas da lista de verificação.

## <a name="relationships"></a>Relacionamentos

Se a sua organização usa uma hierarquia de matriz ou outra hierarquia personalizada, você pode configurar tipos de hierarquia de cargo. Depois disso, você pode adicionar relações de subordinação a cargos para cada tipo de hierarquia configurado. Por exemplo, Lori Penor é um gerente geral na Adventure Works e recebeu o cargo de **Gerente geral**. Lori gerencia o desenvolvimento de um produto usado para limpar widgets. Ela precisa de um contador para ajudá-la com as finanças. Portanto, ela recrutou Kim Akers para ser sua contadora. Kim responde diretamente a Sanjay Patel, mas também trabalha com Lori Penor em seu trabalho relacionado às finanças para desenvolver o limpador de widgets.

Para o exemplo anterior, você deve completar as seguintes tarefas para configurar a relação de subordinação entre Kim Akers e Lori Penor:

1. Crie um tipo de hierarquia de cargos personalizado que é chamado **Widget** para criar uma hierarquia que inclui cargos que são responsáveis por trabalhar no limpador de widgets.
2. Especifique o cargo **Gerente geral** como o cargo a quem Kim responde na hierarquia **Widget**.
3. Use a hierarquia de cargos para exibir a estrutura de subordinação dos cargos. Se você tiver várias hierarquias de cargos, poderá exibir a hierarquia para cada tipo de hierarquia na hierarquia de cargos. Você também pode procurar um cargo por ID do cargo ou pelo nome do trabalhador que está atribuído ao cargo. A hierarquia de cargos é uma hierarquia organizacional.

## <a name="labor-union"></a>Sindicato

Você pode registrar se um contrato de sindicato é necessário para o cargo e qual Sindicato Trabalhista é usado. Você também pode associar o contrato a uma entidade legal.

## <a name="financial-dimensions"></a>Dimensões financeiras

Ao criar a dimensão financeira para um cargo, você deve especificar uma entidade legal. Você pode selecionar as dimensões padrão para cada dimensão individualmente. Como alternativa, você pode selecionar um modelo de distribuição para preencher automaticamente as dimensões padrão. Um modelo de distribuição também oferece a opção de alocar valores por vários valores de dimensão.
