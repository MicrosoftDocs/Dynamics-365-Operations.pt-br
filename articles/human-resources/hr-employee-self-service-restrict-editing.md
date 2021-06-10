---
title: Restringir a edição de informações pessoais
description: Restringir a edição de detalhes de contato por funcionários no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e43b9127b247fa618558b725837d12bf290662f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052016"
---
# <a name="restrict-editing-of-personal-information"></a>Restringir a edição de informações pessoais

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

Este tópico descreve como restringir a edição de detalhes do contato por funcionários no Dynamics 365 Human Resources. Talvez você queira evitar que os funcionários editem certos detalhes do contato, como local de negócios ou endereço de email.

> [!NOTE]
> Para usar esse recurso, você deve primeiro habilitar **(Versão preliminar) Restringir a adição ou edição de informações de endereço e contato por funcionários para fins de seleção** no Gerenciamento de recursos. Para obter mais informações sobre como habilitar os recursos de visualização, consulte [Gerenciar recursos](hr-admin-manage-features.md).<br><br>![Habilitar recursos de visualização](./media/hr-employee-self-service-restrict-enable.png)

## <a name="choose-the-information-an-employee-can-add-or-edit"></a>Escolher as informações que um funcionário pode adicionar ou editar

1. No Human Resources, selecione **Gerenciamento de pessoal**, **Links** e **Parâmetros do Human Resources**.

   ![Acesse Parâmetros de recursos humanos](./media/hr-employee-self-service-human-resources-parameters.png)

2. Na página **Parâmetros de recursos humanos**, selecione a guia **autoatendimento para funcionários**.

   ![Selecione Autoatendimento para funcionários](./media/hr-employee-self-service-tab.png)

3. Na guia **Autoatendimento para funcionários**, desmarque todas as informações na seção **Informações de endereço e contato** que você não deseja que funcionários adicionem ou editem. Neste exemplo, desmarcamos informações de contato **comercial**.

   ![Restringir edição para informações de contato comercial](./media/hr-employee-self-service-restrict-business.png)

4. Selecione **Salvar**.

   ![Salvar alterações](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a>Experiência do funcionário

Após você restringir a adição ou edição de detalhes de contato por funcionários, eles poderão ver as informações, mas não alterá-las.

Neste exemplo, em que os funcionários são impedidos de editar detalhes de contato **comercial**, eles ainda podem ver as informações em Autoatendimento para funcionários:

![Exibir detalhes do contato comercial](./media/hr-employee-self-service-restrict-view.png)

No entanto, quando eles selecionam os detalhes do contato comercial, o painel **Editar endereço** aparece como somente leitura e eles não podem alterar os campos.

![Detalhes do contato comercial são exibidos como somente leitura](./media/hr-employee-self-service-restrict-read-only.png)

Além disso, se selecionarem **Adicionar** para adicionar um novo endereço, eles não poderão selecionar **Comercial** na caixa suspensa **Finalidade**.

![O funcionário não pode adicionar um endereço comercial](./media/hr-employee-self-service-restrict-add.png)

Os funcionários obtêm a mesma experiência quando selecionam **Detalhes do contato** na página **Informações pessoais** e adicionam um novo endereço. A caixa suspensa **Finalidade** só exibe os tipos de informações que podem ser adicionados. 

![O funcionário não pode selecionar Comercial na lista suspensa Finalidade](./media/hr-employee-self-service-restrict-purpose.png)

**Detalhes do contato** agora mostram **Finalidade** na grade.

![Finalidade é exibido na grade de detalhes Contato](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a>Consulte também

[Visão geral de Autoatendimento para funcionários e gerentes](hr-employee-manager-self-service-overview.md)<br>
[Configurar parâmetros de recursos do Human Resources](hr-setup-parameters.md)<br>
[Editar informações pessoais](hr-employee-manager-self-service-edit-personal-information.md)