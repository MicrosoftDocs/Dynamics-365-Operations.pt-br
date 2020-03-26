---
title: Acumular planos de licença e ausência
description: Você pode acumular licenças e ausências no Dynamics 365 Human Resources para vários funcionários ou para uma pessoa.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba60fc2e5b17ec32aa6ad7eb104e8ae55ddee3bb
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092329"
---
# <a name="accrue-leave-and-absence-plans"></a>Acumular planos de licença e ausência

Você pode acumular licenças e ausências no Dynamics 365 Human Resources para vários funcionários ou para uma pessoa.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Acumular licenças e ausências para vários funcionários

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Gerenciar licença**, selecione **Acumular planos de licença e ausência**.

3. Na caixa de diálogo **Acumular planos de licença e ausência**, em **Acumular a partir de**, selecione **Data de hoje** ou selecione **Data personalizada** e digite uma data personalizada.

4. Se você deseja executar o processo de acúmulo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:

   1. Insira informações para o processo de acúmulo.

   2. Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.

   3. Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.

   4. Selecione **OK**. O processo de acúmulo será executado com os parâmetros definidos por você.

## <a name="accrue-leave-and-absence-for-an-employee"></a>Acumular licenças e ausências para um funcionário

1. No registro do funcionário, selecione **Licença**.

2. Selecione **Acumular licenças e ausências**.

3. Na caixa de diálogo **Acumular planos de licença e ausência**, em **Acumular a partir de**, selecione **Data de hoje** ou selecione **Data personalizada** e digite uma data personalizada.

4. Se você deseja executar o processo de acúmulo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:

   1. Insira informações para o processo de acúmulo.

   2. Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.

   3. Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.

   4. Selecione **OK**. O processo de acúmulo será executado com os parâmetros definidos por você.

## <a name="preview-features-for-leave-and-absence"></a>Visualizar recursos para licença e ausência

[!include [banner](includes/preview-feature-leave-absence.md)]

Você pode habilitar os seguintes recursos de visualização para licença e ausência:

- **Excluir acúmulos de licença e ausência**. Exclua os registros de acúmulo para um plano e um intervalo de datas específicos. As datas de acúmulo devem ser datadas hoje ou no futuro.

- **Auditoria do acúmulo de licenças**. Exibido sempre que alguém executa ou exclui um acúmulo para um ou todos os funcionários, junto com a data e quem realizou a ação.

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
- [Criar um plano de licença e ausência](hr-leave-and-absence-plans.md)