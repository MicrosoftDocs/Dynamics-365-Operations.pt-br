---
title: Configurar habilidades
description: Você pode rastrear as habilidades de seu trabalhador no Dynamics 365 Human Resources. Você também pode especificar as habilidades necessárias para um trabalho específico.
author: twheeloc
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 7c853ad71aecd7f5d214c02da97f7956ff2391df
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695946"
---
# <a name="configure-skills"></a>Configurar habilidades

> [!IMPORTANT]
> A funcionalidade mencionada neste tópico está disponível atualmente para clientes do Human Resources na infraestrutura do Finance.  


Você pode rastrear as habilidades de seu trabalhador no Dynamics 365 Human Resources. Você também pode especificar as habilidades necessárias para um trabalho específico.

Os exemplos das habilidades que você pode rastrear incluem:

- Supervisão – capacidade de supervisionar o trabalho de terceiros.
- Liderança – capacidade de liderar funcionários e setores empresariais.
- Planejamento - capacidade de antever o futuro, formular instruções de visões e acompanhá-las.
- HTML – Capacidade de gravar o código HTML.

Se você ainda não configurou os tipos de habilidades e os modelos de classificação, será necessário adicionar algum antes de criar habilidades.

As seguintes pessoas podem inserir habilidades para um trabalhador:

- Os trabalhadores podem inserir habilidades para si mesmos no Autoatendimento para funcionários. Essas habilidades exigem aprovação do gerente.
- Os gerentes podem inserir habilidades para seus trabalhadores. Você pode criar um fluxo de trabalho que aprova essas habilidades automaticamente.

## <a name="create-a-skill-type"></a>Criar um tipo de habilidade

Os tipos de habilidades são categorias sob as quais as habilidades individuais se encaixam, como Administração ou Vendas.

1. No espaço de trabalho **Desenvolvimento do funcionário**, selecione **Links**.

2. Em **Configuração de competência**, selecione **Tipos de habilidades**.

3. Selecione **Novo**.

4. Complete os campos a seguir:

   - **Tipo de habilidade**: informe um nome para o tipo de habilidade.
   - **Descrição**: informe uma descrição para o tipo de habilidade.

5. Selecione **Salvar**.

## <a name="create-a-rating-model"></a>Criar um modelo de classificação

Os modelos de classificação ajudam a avaliar o nível real de habilidades de uma pessoa, o nível que ela deveria atingir ou o nível de habilidades necessário para um trabalho. Cada nível em um modelo de classificação é atribuído um fator.

1. No espaço de trabalho **Desenvolvimento do funcionário**, selecione **Links**.

2. Em **Configuração de competência**, selecione **Modelos de classificação**.

3. Selecione **Novo**.

4. Complete os campos a seguir:

   - **Classificação**: insira um nome para o modelo de classificação, por exemplo, **Habilidades**.
   - **Descrição**: insira uma descrição para o modelo de classificação, como **Classificações de habilidade**.

5. Na seção **Níveis**, selecione **Novo**. Para cada nível a ser adicionado, preencha os seguintes campos:

   - **Nível**: informe um nome para o nível.
   - **Descrição**: insira uma descrição para o nível.
   - **Fator**: insira um valor de fator de 0-9. Os fatores ajudam a normalizar as pontuações das habilidades que usam diferentes modelos de avaliação. Cada nível deve ter um fator exclusivo. Os níveis com valores de fator mais altos têm mais peso em um modelo de avaliação.

   Continue adicionando níveis, conforme a necessidade. É possível inserir até 10 níveis para cada modelo de avaliação.

6. Selecione **Salvar**.

## <a name="create-a-skill"></a>Criar uma habilidade

Antes de atribuir uma habilidade ou criar uma pesquisa de mapeamento de habilidades ou perfil de habilidades, você deve inserir informações sobre as habilidades na página **Habilidades**. Para cada habilidade, você pode selecionar um tipo de habilidade e um modelo de classificação.

1. No espaço de trabalho **Desenvolvimento do funcionário**, selecione **Links**.

2. Em **Configuração de competência**, selecione **Habilidades**.

3. Selecione **Novo**.

4. Complete os campos a seguir:

   - **Habilidade**: informe um nome para a habilidade.
   - **Descrição**: informe uma descrição para a habilidade.
   - **Classificação**: selecione o modelo de classificação que você deseja usar para esta habilidade.
   - **Tipo de habilidade**: selecione na lista de tipos de habilidades.

5. Selecione **Salvar**.

## <a name="see-also"></a>Consulte também

[Inserir habilidades](hr-develop-enter-skills.md)<br>
[Mapear habilidades](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
