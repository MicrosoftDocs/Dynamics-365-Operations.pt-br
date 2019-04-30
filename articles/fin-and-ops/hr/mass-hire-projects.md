---
title: Projetos de contratação em massa
description: Os projetos de contratação em massa permitem que especialistas em recursos humanos criem várias posições e contratem com eficiência trabalhadores para essas posições.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7dacc8b0ca8659d3ae69c81385918ef6fa39c04
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "858942"
---
# <a name="mass-hire-projects"></a>Projetos de contratação em massa

[!include [banner](../includes/banner.md)]

Os projetos de contratação em massa permitem que especialistas em recursos humanos criem várias posições e contratem com eficiência trabalhadores para essas posições.

## <a name="overview"></a>Visão Geral

Ao contratar vários funcionários em algum momento, como ocorre em contratações para atender uma demanda sazonal, é útil criar um projeto de contratação em massa. Criar um projeto de contratação em massa é útil porque você pode criar registros de posições, registros de funcionário, e as atribuições de trabalho para posições ao mesmo tempo. A o criar posições para um projeto de contratação em massa, você poderá especificar as seguintes informações:

- O número de posições adicionais a serem criadas
- O tipo de trabalho das pessoas que você envolverá para as posições
- Selecione o trabalho e o departamento associado às posições.
- O valor equivalente a posição de tempo integral

## <a name="example"></a>Exemplo

Em o verão, você contrata geralmente 15-20 estudantes universitário de meio expediente preencha fases disponíveis em sua empresa. Este ano, você deseja contratar cinco contadores, cinco processadores da ordem, e os caixas. Em vez de criar cada registro de posição e registro de trabalhador separadamente, você cria um projeto de contratação em massa denominado "SummerInterns". As datas inicial e final do projeto estão correlacionadas ao início e fim final de durações de posição para as posições criadas para o projeto de contratação em massa.

Na página **Projetos de contratação em massa**, selecione o projeto "SummerInterns" e clique em **Abrir projeto**. No projeto de contratação em massa aberto, clique em **Criar posições** e insira informações sobre a posição de contador. Você pode indicar que cinco posições de contador devem ser criadas usando as mesmas informações e então clique em OK. Repita este processo para as posições de processamento e de caixa da ordem.

Depois de selecionar alunos para contratar para posições de estágio, insira as informações de cada aluno nos **Detalhes da posição** para a posição para a qual eles estão sendo contratados. Depois de inserir todos os detalhes da posição, selecione a posição na página Projetos de contratação em massa e clique em **Contratar**. Um registro de posições será criado para cada cargo e um registro de funcionário será criado e o atribuiu a posição correta para cada pessoa que você contrata.

## <a name="mass-hire-project-statuses"></a>Status do projeto de contração em massa

um projeto de contratação em massa pode ter os seguintes status.

- Criado em
- Abertas
- Fechado

Na página **Projeto de contratação em massa**, clique em **Abrir projeto** ou em **Fechar projeto** para alterar o status de um projeto de contratação em massa. A tabela a seguir descreve o que é possível fazer com um projeto de acordo com seu status.

<table>
<thead>
<tr>
<th>Status</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr>
<td>Criado em</td>
<td>É possível criar e modificar informações, mas não é possível criar linhas para o projeto. Este é o status padrão de novos projetos.</td>
</tr>
<tr>
<td>Abertas</td>
<td>Você pode alterar os detalhes do projeto, para criar posições para o projeto de contratação em massa, e pessoas de contratação para posições. Este é o status de projetos ativos.</td>
</tr>
<tr>
<td>Fechado</td>
<td>Não é possível adicionar posições ao projeto. Para adicionar posições ao projeto de contratação em massa, abra-o novamente. Este é o status de projetos concluídos.
<blockquote>[!NOTE] Para fechar um projeto de contratação em massa, todas as linhas do projeto deverão ter o status Criado ou Fechado.</blockquote>
</td>
</tr>
</tbody>
</table>
