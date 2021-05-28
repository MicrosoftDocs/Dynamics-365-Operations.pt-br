---
title: Alterar ou reatribuir um calendário do razão
description: Este tópico explica como alterar o calendário que está atribuído no momento a um razão e como atribuir um novo calendário ao razão.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 052b8944c0a015187d1d7c4ba3db878c52faeeea
ms.sourcegitcommit: 905a8c7a0c1bc06ada2acfba913dfe5f7b44ea16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6039941"
---
# <a name="change-or-reassign-a-ledger-calendar"></a>Alterar ou reatribuir um calendário do razão

[!include [banner](../includes/banner.md)]

Este tópico explica como alterar o calendário que está atribuído no momento a um razão e como atribuir um novo calendário ao razão.

## <a name="issue"></a>Problema

Às vezes, as empresas devem alterar o calendário existente atribuído a um razão ou atribuir um novo calendário.

## <a name="resolution"></a>Resolução

Há dois cenários para alterar ou reatribuir um calendário do razão. O primeiro cenário envolve a alteração de um calendário existente que já está atribuído ao razão. O segundo cenário envolve a criação de um calendário e sua atribuição ao razão. Ambas as alterações podem ser feitas a qualquer momento, mesmo depois que as transações tiverem sido lançadas no razão.

### <a name="change-an-existing-fiscal-calendar"></a>Alterar um calendário fiscal existente

Para alterar um calendário existente atribuído ao seu razão, acesse **Contabilidade \> Configuração do razão \> Razão** e selecione o link para o calendário fiscal para abrir a página **Calendários do razão**.

Existem limites para as alterações que podem ser feitas em um calendário. Por exemplo, você pode alterar as datas de início e término dos *períodos* em um ano, mas não pode alterar as datas de início e término de um *ano* no calendário.

Para alterar os períodos em um ano, selecione o calendário e o ano apropriados. Primeiro, use o botão **Excluir período** para excluir alguns ou todos os períodos operacionais existentes. É possível excluir todos os períodos operacionais, exceto o primeiro. Em seguida, use o botão **Dividir período** para dividir o período ou os períodos restantes em novos períodos inserindo uma data de início apropriada para o próximo período.

Depois de alterar os períodos em um calendário, você deve executar o processo **Recalcular períodos do razão** em cada entidade legal (empresa) à qual o calendário está atribuído. Embora nenhuma mensagem de aviso lembre-o de concluir essa etapa, o processo de recálculo é necessário para atualizar o período atribuído a cada transação lançada na Contabilidade. Para executar o processo de recálculo, selecione **Recalcular períodos do razão** na página **Configuração do razão** em cada empresa.

Se o processo de recálculo não for executado, os saldos da transação em um balancete ou nos demonstrativos financeiros podem ser incluídos incorretamente nos períodos. Nesse caso, você pode corrigir os saldos a qualquer momento executando o processo de recálculo.

### <a name="assign-a-new-fiscal-calendar"></a>Atribuir um novo calendário fiscal

Para atribuir um novo calendário fiscal, acesse **Contabilidade \> Configuração do razão \> Razão** e selecione **Editar** para colocar a página **Razão** no modo de edição. Em seguida, no campo **Calendário fiscal**, selecione um novo calendário fiscal.

Depois de alterar o calendário fiscal de um razão, você deve executar a opção **Recalcular períodos do razão**. Quando você atribui um novo calendário fiscal a um razão, uma mensagem lembrará você de concluir essa etapa. Embora a mensagem pareça indicar que o processo de recálculo é opcional, ele não é. É necessário atualizar o período que está atribuído a cada transação lançada na Contabilidade. Para executar o processo de recálculo, selecione **Recalcular períodos do razão** na página **Configuração do razão**.

Se o processo de recálculo não for executado, os saldos da transação em um balancete ou nos demonstrativos financeiros podem ser incluídos incorretamente nos períodos. Nesse caso, você pode corrigir os saldos a qualquer momento executando o processo de recálculo.
