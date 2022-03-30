---
title: Configure informações sobre grupo TDS, PANs e TANs para fornecedores e clientes
description: Este tópico explica como configurar informações sobre grupos de Imposto Deduzido na Origem (TDS), número de conta permanente (PAN) e número de conta de imposto (TAN) para fornecedores e clientes.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 808fa7b72651ab274415e48f5e0a356784ca6525
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407527"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>Configuração de informações do grupo TDS, PAN e TAN para fornecedores e clientes

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar informações sobre grupos de Imposto Deduzido na Origem (TDS), número de conta permanente (PAN) e número de conta de imposto (TAN) para fornecedores e clientes.

1. Acesse **Contas a pagar \> Fornecedores \> Todos os fornecedores** ou **Contas a receber \> Clientes \> Todos os clientes**.

    [![Página Todos os fornecedores.](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. No Painel de Ações, selecione **Novo** para criar um fornecedor ou cliente e insira os detalhes necessários. Alternativamente, selecione um fornecedor ou cliente existente.
3. Na FastTab **Fatura e entrega**, na seção **Imposto retido na fonte**, defina a opção **Calcular imposto retido na fonte** como **Sim** para calcular a retenção de imposto, TDS ou Impostos Recolhidos na Fonte (TCS) para o fornecedor ou cliente.
4. O TDS para uma fatura de compra é calculado com base no grupo de TDS padrão definido para o fornecedor ou cliente. No campo **Grupo de TDS**, selecione o grupo de TDS padrão.

    > [!NOTE]
    > Quando você seleciona um grupo de TDS no campo **Grupo de TDS**, os campos **Grupo de impostos retidos na fonte** e **Grupo de TCS** ficam indisponíveis.

5. Na FastTab **Informações sobre imposto**, na seção **Informações sobre PAN**, no campo **Status**, selecione o status do número da conta permanente para o fornecedor ou cliente:

    - **Não disponível** – o fornecedor ou o cliente não tem um PAN.
    - **Recebido** – O fornecedor ou o cliente tem um PAN.
    - **Aplicado** – o fornecedor ou o cliente se aplicou para um PAN.
    - **Inválido** – o fornecedor ou o cliente tem um PAN, mas ele não é válido.

6. Se você selecionou **Recebido** no campo **Status** para indicar que o fornecedor ou o cliente tem um PAN, insira o PAN no campo **Número**. O PAN deve consistir em cinco caracteres alfabéticos, quatro caracteres numéricos e, depois, um caractere alfabético. Veja aqui um exemplo: **ABCDE1260A**.
7. Se você selecionou **Aplicado** no campo **Status** para indicar que o fornecedor ou cliente aplicou PAN, informe o número de referência no campo **Número de referência**.
8. No campo **Natureza do avaliado**, selecione a natureza da categoria do avaliado à qual o fornecedor ou cliente pertence:

    - Empresa
    - HUF
    - Confirmar
    - Pessoa física
    - AOP
    - BOI
    - Autoridade local
    - Diversos

    [![FastTab Informações sobre imposto.](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. No Painel de Ações, na guia **Fornecedor**, no grupo **Registro**, selecione **IDs de Registro** para abrir a página **Gerenciar endereços**.
10. Na página **Gerenciar endereços**, na FastTab **Informações sobre imposto**, selecione **Adicionar** ou **Editar** para abrir a página **Gerenciar informações sobre imposto**, na qual é possível manter a entrada do registro de imposto.
11. Na página **Gerenciar informações sobre imposto**, na FastTab **Imposto retido na fonte**, no campo **Número da Conta de Imposto (TAN)**, insira o TAN. O TAN deve consistir em quatro caracteres alfabéticos, cinco caracteres numéricos e, depois, um caractere alfabético. Veja aqui um exemplo: **AFGH54821T**.
12. Feche a página.
