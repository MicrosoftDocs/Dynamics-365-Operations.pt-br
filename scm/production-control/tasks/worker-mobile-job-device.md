--- 
title: "Configurar um trabalhador usando um dispositivo de trabalho móvel"
description: "Este procedimento mostra como atribuir as funções corretas na conta de usuário de um trabalhador e, em seguida, habilitá-lo para fazer registros de chão de fábrica."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 7da224809946d90387668d25c5aed5b61f6a7b72
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Configurar um trabalhador usando um dispositivo de trabalho móvel

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como atribuir as funções corretas na conta de usuário de um trabalhador e, em seguida, habilitá-lo para fazer registros de chão de fábrica.


## <a name="assign-roles-to-user-account"></a>Atribua funções à conta do usuário
1. Vá para Administração do sistema > Usuários > Usuários.
2. Use o Filtro Rápido para filtrar pelo nome de um trabalhador no qual a conta de usuário está associada à função do operador de máquina. Nos dados de exemplo, o nome será Shannon.
3. Realce o registro da conta de usuário.
4. Na lista, clique no link “Nome” na linha selecionada para exibir os detalhes da conta de usuário.
5. Na árvore, selecione 'Funções\operador de Máquina'.
6. Feche a página detalhes da conta de usuário.
7. Feche a página.

## <a name="configure-worker-account"></a>Configure a conta do trabalhador.
1. Vá para Recursos humanos > Trabalhadores > Trabalhadores.
2. Use o Filtro Rápido para filtrar pelo nome de um trabalhador no qual a conta de usuário está associada à função do operador de máquina. Nos dados de exemplo, o nome será Shannon.
3. Realce o registro da conta de usuário.
4. Na lista, clique no link “Nome” na linha selecionada para exibir os detalhes da conta de usuário.
5. Clique na guia Emprego.
6. Expanda a Guia Rápida Registro de horário e clique em Ativar nos terminais de registro.
7. Clique em Ativar nos terminais de registro.
8. No campo Grupo de cálculo, insira ou selecione um valor.
9. No campo Grupo de Cálculo Padrão, insira ou selecione um valor.
10. No campo Grupo de Aprovação, insira ou selecione um valor.
11. No campo Perfil Padrão, insira ou selecione um valor.
12. No campo Grupo de Perfil, insira ou selecione um valor.
13. Clique em OK.
14. Clique em Editar para inserir um número do crachá para o novo trabalhador de registro de horário.
15. No campo ID do Crachá, digite um valor.
16. Clique em Salvar.
17. Use o atalho Salvar Registro.
18. Fechar a página de detalhes do trabalhador.
19. Feche a página.

## <a name="assign-worker-to-device-group"></a>Atribua o trabalhador ao grupo de dispositivos.
1. Vá para Controle de Produção > Configuração > Execução de Fabricação > Configurar o Cartão de Trabalho para Dispositivos.
2. Clique em Adicionar.
3. Na lista, marque a linha selecionada.
4. Clique em OK.
5. Clique em Editar.
6. No campo Unidade de Produção, você pode definir o filtro padrão para o trabalhador. Isso garantirá que somente os trabalhos de produção da unidade de produção selecionada serão exibidos quando o trabalhador fizer logon no dispositivo.
7. Feche a página.


