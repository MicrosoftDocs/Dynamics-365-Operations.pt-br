---
title: Os funcionários selecionam usando o Autoatendimento para funcionários (opcional)
description: Este artigo descreve como os funcionários podem selecionar ou atualizar seus benefícios.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 21567851500f4a68e5393b16ccf2b1de00a0ca7a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909952"
---
# <a name="employees-select-plans-by-using-employee-self-service-optional"></a>Os funcionários selecionam usando o Autoatendimento para funcionários (opcional)


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Quando um novo funcionário é contratado ou ocorre um evento de vida, ele pode usar o **Autoatendimento para funcionários** selecionar ou atualizar seus benefícios durante o registro aberto.

Para acessar seus benefícios para registro, o funcionário acessa o **Autoatendimento para funcionários** e seleciona o **Autoatendimento de benefícios** no bloco **Benefícios**.

Na página **Auto-atendimento de benefícios**, os planos de benefícios são agrupados por tipo de plano. Para exibir os planos de benefícios em um tipo de plano, o funcionário deve selecionar um bloco na página **Benefícios do funcionário**. O funcionário verá somente os benefícios para os quais está qualificado.

> [!IMPORTANT]
> Para que um tipo de plano possa ser exibido em **Autoatendimento para funcionários**, ele deve ser configurado. Para obter mais informações, consulte [Configurar o Autoatendimento para funcionários](/dynamics365/human-resources/hr-benefits-setup-employee-self-service).

Dependendo do tipo de plano, uma ou mais vantagens podem ser selecionadas para registro. Por exemplo, um tipo de plano médico pode ser configurado para limitar o funcionário a um plano médico. Um tipo de plano de seguro de vida pode permitir que o funcionário selecione vários planos de seguro de vida.

Depois que o funcionário decidir em qual plano se inscrever, talvez seja necessário selecionar dependentes. Se o funcionário selecionou uma opção de cobertura que é **Funcionário +1**, **Funcionário + filho** ou **Família**, dependentes deverão ser selecionados. Para obter mais informações sobre opções de cobertura, consulte [Criar opções de cobertura](/dynamics365/human-resources/hr-benefits-setup-coverage-options).

Para selecionar um plano de benefícios, o funcionário deve selecionar o botão de reticências (**...**) ou **Adicionar ao carrinho**. Depois que o funcionário terminar de adicionar todas as seleções de benefícios ao carrinho, ele deve selecionar **Exibir carrinho**. Em seguida, o funcionário é direcionado para a página **Planos**, na qual é possível exibir os planos de benefícios selecionados e renunciados.

O funcionário deve selecionar a opção **Concordo** para que possa selecionar o botão **Finalizar Compra**. O demonstrativo exibido à direita da opção **Concordo** pode ser personalizado na guia **Gerenciamento de benefícios** da página **Parâmetros Compartilhados do Human Resources**.

Quando o funcionário confirma suas seleções de plano de benefícios usando o **Autoatendimento para funcionários**, essas seleções são registradas e exibidas nas páginas **Planos de benefícios para o trabalhador** e **Atualização em massa dos planos de benefícios do trabalhador**.

Depois que o funcionário seleciona os planos, o status dos benefícios é exibido como **Selecionado**. Quando o funcionário selecionar **Finalizar Compra** na página **Autoatendimento de benefícios**, a opção **Finalizar Compra** será selecionada.

> [!IMPORTANT]
> Para concluir o registro, o administrador de benefícios deve selecionar **Confirmar** para cada benefício de funcionário selecionado. A confirmação pode ser concluída na página **Plano de benefícios do trabalhador** ou **Atualização em massa dos planos de benefícios do trabalhador**.
>

Não é necessário que os funcionários selecionem benefícios usando o **Autoatendimento para funcionários**. Os benefícios podem ser selecionados em nome de um funcionário na página **Plano de benefícios do trabalhador** ou **Atualização em massa dos planos de benefícios do trabalhador**. O funcionário não será registrado nesses benefícios até que o administrador de benefícios os confirme.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
