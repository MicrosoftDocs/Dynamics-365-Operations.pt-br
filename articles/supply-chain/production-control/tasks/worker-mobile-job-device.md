---
title: Configurar um trabalhador usando um dispositivo de trabalho móvel
description: Este tópico explica como atribuir as funções corretas na conta de usuário de um trabalhador e, em seguida, habilitá-lo para fazer registros de chão de fábrica.
author: ShylaThompson
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ada42a98a8a87e377f939d063b17f9904f6b3408
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422349"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Configurar um trabalhador usando um dispositivo de trabalho móvel

[!include [banner](../../includes/banner.md)]

Este tópico explica como atribuir as funções corretas na conta de usuário de um trabalhador e, em seguida, habilitá-lo para fazer registros de chão de fábrica.

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a>Verificar se um trabalhador teve uma determinada função atribuída a ele

Por exemplo, verifique se a usuária "SHANNON" obteve a função de operadora de máquina antes de configurar a conta de trabalhador.

1. Vá para **Painel de navegação > Módulos > Administração do sistema > Usuários > Usuários**.
2. Procure um usuário no filtro rápido. Neste exemplo, insira `shannon`.
3. Selecione o link na coluna **ID do usuário** da conta de usuário que aparece.
4. Na árvore **Funções do usuário**, selecione **Funções > Operador de máquina**.
5. Feche as páginas **detalhes do usuário** e **usuários** para retornar à home page.

## <a name="configure-worker-account"></a>Configurar a conta do trabalhador
1. Vá para **Painel de navegação > Módulos > Recursos humanos > Trabalhadores > Trabalhadores**.
2. Procure um usuário no filtro rápido. Neste exemplo, insira `shannon`.
3. Selecione o link na coluna **Nome** da conta de usuário que aparece.
4. Selecione a guia **Registro de horas**.
5. Selecione **Ativar nos terminais de registro**.
6. Insira ou selecione os valores nos seguintes campos:  

    - **Grupo de cálculo**  
    - **Grupo de cálculos padrão**  
    - **Grupo de aprovação**  
    - **Perfil padrão**  
    - **Grupo de perfis**  

7. Selecione **OK**.
8. Selecione **Editar** para inserir um número do crachá para o novo trabalhador de registro de horário. Insira um valor no campo **ID do Crachá**.
9. Selecione **Salvar**.
10. Feche as páginas **Detalhes do trabalhador** e **Trabalhadores**.

## <a name="assign-worker-to-device-group"></a>Atribuir o trabalhador ao grupo de dispositivos
1. Vá para **Controle de produção > Configuração > Execução de fabricação > Configurar cartão de trabalho para dispositivos**.
2. Selecione **Adicionar**.
3. Na lista, selecione o trabalhador desejado. Neste exemplo, selecione **SHANNON**.
4. Selecione **OK**.
5. Selecione **Editar**.
6. No campo **Unidade de produção**, você pode definir o filtro padrão para o trabalhador. Isso garantirá que somente os trabalhos de produção da unidade de produção selecionada serão exibidos quando o trabalhador fizer logon no dispositivo. Insira o valor desejado.
7. Feche a página.

