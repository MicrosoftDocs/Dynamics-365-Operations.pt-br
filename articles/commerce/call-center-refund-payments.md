---
title: Reembolsar processamento de pagamentos em call centers
description: Este tópico explica como os reembolsos de pagamentos são gerados por call centers quando devoluções são criadas ou quando ordens ou linhas de ordem são canceladas.
author: hhainesms
manager: annbe
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3f98fbc14fc2946499a9c003eb0bd0edb7f2017e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991406"
---
# <a name="refund-payment-processing-in-call-centers"></a>Reembolsar processamento de pagamentos em call centers

Este tópico explica como os reembolsos de pagamentos são gerados por call centers quando devoluções são criadas ou quando ordens ou linhas de ordem são canceladas.

Um usuário que cria uma ordem de devolução para um cliente como um usuário do call center na sede do Microsoft Dynamics 365 Commerce usa a página **Ordem de devolução** para criar a autorização para devolução de materiais (RMA) inicial. A RMA define os produtos que o cliente deseja devolver ou trocar e cria uma ordem de venda de devolução vinculada que tem um tipo de **ordem devolvida**. A ordem devolvida vinculada é usada para rastrear o lançamento do estoque devolvido e notas de crédito ou reembolsos de pagamento que são lançados.

Se a opção **Habilitar conclusão de ordem** estiver definida como **Sim** para o canal de call center, o usuário do call center que cria a RMA deverá executar o fluxo de processamento da conclusão da ordem, selecionando **Concluir** na página **Ordem de devolução**. A função **Concluir** fornece um resumo de reembolso calculado que descreve o valor de reembolsos vencidos. Além disso, quando ele é configurado corretamente, cria sistematicamente uma linha de pagamento de reembolso na ordem devolvida.

A lógica do call center determina o método de pagamento da linha de pagamento de reembolso, com base no método de pagamento usado para a ordem original. Se a ordem de devolução criada não estiver vinculada a uma ordem original, será aplicado um método de pagamento padrão obtido de um parâmetro do sistema.

## <a name="how-a-call-center-determines-which-payment-method-to-apply-to-a-return-order"></a>Como um call center determina o método de pagamento a ser aplicado a uma ordem de devolução

O call center usa o método de pagamento da ordem original para determinar o método de pagamento que deve ser aplicado a uma ordem de devolução. Veja como esse processo funciona para os seguintes métodos de pagamento originais:

- **Normal** (pagamento à vista) ou **Cheque** – quando uma ordem de devolução criada faz referência a uma ordem original que foi paga usando o tipo de pagamento normal (à vista) ou em cheque, o aplicativo de call center faz referência a configurações na página **Métodos de reembolso do call center**. Esta página permite que as organizações definam, por moeda da ordem, como os reembolsos são emitidos para clientes para ordens que foram pagas originalmente usando o tipo de pagamento normal ou em cheque. A página **Métodos de reembolso de call center** também permite que as organizações selecionem se um cheque de reembolso gerado pelo sistema é enviado ao cliente ou se um crédito de conta de cliente é criado em relação ao saldo da conta do cliente interno. Nesses cenários, a lógica de call center referencia a moeda da ordem de devolução e usa o valor do **Método de pagamento de varejo** dessa moeda para criar uma linha de pagamento de reembolso na ordem de venda de devolução. Posteriormente, um diário de pagamento de cliente de contas a receber (RA) que usa o método de pagamento RA mapeado é vinculado à moeda.

    A ilustração a seguir mostra a configuração de um cenário em que um cliente devolve produtos de uma ordem de venda vinculada à moeda USD e que foi paga originalmente usando o tipo de pagamento normal ou em cheque. Neste cenário, um reembolso será emitido para o cliente por meio de um cheque de reembolso gerado pelo sistema. O método de pagamento **REF-CHK** foi configurado como um tipo de pagamento de cheque de reembolso.

    ![Configuração dos métodos de reembolso de call center para pagamentos originais normal e em cheque](media/callcenterrefundmethods.png)

- **Cartão de crédito** – quando uma ordem de devolução criada faz referência a uma ordem original que foi paga usando um cartão de crédito, a lógica de call center para pagamentos de reembolso aplica o mesmo cartão de crédito original à ordem de devolução.
- **Cartão-fidelidade** – quando uma ordem de devolução criada faz referência a uma ordem original que foi paga usando um cartão-fidelidade, a lógica de call center para pagamentos de reembolso aplica o reembolso mesmo cartão-fidelidade.
- **Cartão-presente** (interno) – quando uma ordem de devolução criada faz referência a uma ordem original que foi paga usando um vale-presente emitido do Dynamics 365 Commerce (funcionalidade interna de cartão-presente), a lógica de call center para pagamentos de reembolso aplica o reembolso ao mesmo número do vale-presente original.
- **Cartão-presente** (externo) – quando uma ordem de devolução criada faz referência a uma ordem original que foi paga usando um cartão-presente externo de terceiros, a lógica de call center para pagamentos de reembolso aplica o método de pagamento de devolução padrão definido na guia **RMA/devolução** da página **Parâmetros de call center**.

Se o tipo de pagamento da ordem original for desconhecido por algum motivo ou se vários métodos de pagamento forem usados para pagar a ordem original, a lógica de call center aplicará o método de pagamento de devolução padrão definido na guia **RMA/devolução** da página **Parâmetros de call center**.

A ilustração a seguir mostra o campo **Método de pagamento** na guia **RMA/devolução** da página **Parâmetros de call center**.

![Campo Método de pagamento na guia RMA/devolução da página Parâmetros de call center](media/callcenterrefundparameters.png)

> [!NOTE]
> As regras de processamento de reembolso descritas anteriormente também se aplicam a ordens ou linhas de ordem que um usuário de call center cancela na sede do Commerce. Se o cancelamento de uma ordem ou linhas de ordem específicas gerarem pagamentos excedente, as mesmas regras serão usadas para gerar linhas de pagamento de reembolso.

Normalmente, uma ordem de devolução passa por um processo padrão, no qual o estoque é recebido (ou descartado), uma guia de remessa é lançada na ordem de devolução e um processo de lançamento de fatura é executado para a ordem de venda de devolução. A ordem de venda de devolução é vinculada e gerada sistematicamente como parte do processo de criação da ordem de devolução. Em cenários típicos, os reembolsos de pagamento não são emitidos para clientes até que a fatura da ordem de venda de devolução seja lançada.

### <a name="what-happens-when-an-invoice-is-posted-on-a-return-sales-order"></a>O que acontece quando uma fatura é lançada em uma ordem de venda de devolução

Os seguintes cenários explicam o que acontece quando uma fatura é lançada em uma ordem de venda de devolução:

- Se o pagamento de reembolso na ordem de devolução for para um cartão de crédito, a lógica adicional será invocada quando a fatura for lançada. Essa lógica chama o processador de pagamento para reembolsar o pagamento para o cartão de crédito do cliente. Um comprovante de pagamento de cliente de reembolso também é criado e lançado sistematicamente na conta do cliente. Este diário de pagamentos será liquidado em relação ao comprovante da nota de crédito da ordem de devolução.
- Se o pagamento de reembolso que deve ser emitido for para o tipo de pagamento de cheque, um comprovante de pagamento de cliente que usa o método de pagamento AR será criado e deverá ser lançado manualmente ou impresso antes que o comprovante de pagamento possa ser lançado na conta do cliente. Para processar a verificação de reembolso, os usuários podem usar a página **Diário de pagamentos do cliente** em Contas a receber ou na página **Processamento de verificação de reembolso** especializada no Retail e Commerce.
- Se o pagamento de reembolsos a ser emitido for para o tipo de pagamento do cartão-presente ou do cartão-fidelidade, quando a ordem de devolução for faturada, o comprovante de pagamento de reembolso será criado e lançado na conta do cliente. Esta etapa de faturamento também adiciona o valor do reembolso de volta ao saldo do cartão-presente ou de pontos de fidelidade controlado internamente pelo cliente.
- Se um método de pagamento que usa a função **Cliente** (por exemplo, uma conta de cliente) estiver vinculado à ordem de venda de devolução, as validações de limite de crédito serão ignoradas quando o pagamento for processado. Nenhum comprovante de pagamento é criado ou lançado neste contexto. Quando um tipo de pagamento de cliente é usado em uma ordem de devolução, o comprovante de nota de crédito que o processo de lançamento de fatura cria serve como o comprovante de crédito do cliente e indica um reembolso para o saldo de AR do cliente.

## <a name="advance-credit"></a>Crédito antecipado

Quando um usuário processa ordens de devolução como um usuário de call center em uma call center onde a opção **Habilitar a conclusão da ordem** está definida como **Sim**, uma exceção do processo descrito anteriormente para lançamento de pagamento de reembolso poderá ocorrer se o usuário do call center que estiver criando a ordem de devolução definir a opção **Crédito antecipado** como **Sim** na guia **RMA/devolução** da página **Parâmetros de call center**. Nesse caso, o reembolso de pagamentos ocorre logo depois que a ordem de devolução é enviada com êxito usando a função **Enviar** na página **Resumo de devolução**. O sistema cria imediatamente um comprovante de pagamento de cliente para pagamento antecipado para o valor de retorno, mesmo que a ordem de venda de devolução ainda não tenha sido faturada. Essa abordagem pode ser usada em situações em que uma organização deve emitir reembolsos para clientes com antecedência por questões de atendimento ao cliente e não deseja exigir que o estoque devolvido seja recebido antes da emissão de reembolsos.

## <a name="replacement-orders"></a>Ordens de substituição

Quando uma ordem de devolução é emitida, a função **Ordem de substituição** pode ser usada para gerar uma nova ordem de venda para o cliente. Esta abordagem pode ser usada em cenários de troca. A função **Ordem de substituição** cria uma outra ordem de venda para os novos itens que devem ser enviados, mas um link de referência cruzada na guia **RMA/devolução** da página **Parâmetros de call center** vincula a ordem de substituição, a RMA e a ordem de venda devolvida.

Quando os pagamentos em uma ordem de substituição são processados, as organizações têm duas opções:

- Reembolsar o cliente pela ordem de devolução, com base no método de pagamento original e, depois, coletar um pagamento separado para a ordem de substituição. Nenhuma configuração adicional é necessária para usar esta opção.
- Defina a opção **Aplicar crédito** como **Sim** na guia **RMA/devolução** da página **Parâmetros de call center**. Nesse caso, um método de pagamento de cliente é sistematicamente aplicado na ordem de devolução e na ordem de substituição. Esta opção pode ajudar a impedir que pagamentos de reembolso externos sejam emitidos. Ela também ajuda a evitar processamentos de pagamentos na transação. Ela pode ser útil em situações em que uma troca está sendo processada, e a organização prefere usar o comprovante de crédito que é gerado quando a ordem de devolução é faturada para pagar pela fatura que é gerada pela ordem de substituição. Quando a opção **Aplicar crédito** estiver definida como **Sim**, a organização deverá liquidar manualmente a nota de crédito em relação à fatura da ordem de substituição depois que os documentos financeiros tiverem sido gerados.

Uma configuração **Sim** para a opção **Aplicar crédito** será aplicável somente quando a ordem de devolução for vinculada a uma ordem de substituição. Nesse caso, o método de pagamento de cliente que será usado para pagar sistematicamente pela devolução e pela ordem de câmbio será definida pelo campo **Aplicar método de pagamento de créditos** na guia **RMA/devolução** da página **Parâmetros de call center**. Somente um pagamento do tipo de pagamento de função **Cliente** pode ser selecionado neste campo.

> [!NOTE]
> Para uma ordem de devolução que não tenha ordem de substituição vinculada, uma configuração **Sim** para a opção **Aplicar crédito** não terá efeito na lógica de pagamento da ordem de devolução, pois essa configuração se aplica somente a ordens de substituição.

![Campo Aplicar método de pagamento de créditos na guia RMA/devolução da página Parâmetros de call center](media/callcenterrefundparameters1.png)

> [!IMPORTANT]
> Se os usuários que criarem ordens de substituição pretenderem usar a opção **Aplicar crédito**, eles não deverão executar a função **Concluir** na ordem de devolução antes de definir a opção **Aplicar crédito** como **Sim**. Após a execução da função **Concluir**, o pagamento de reembolso será calculado e aplicado à ordem de venda de devolução. Qualquer tentativa de definir a opção **Aplicar crédito** como **Sim** após um pagamento de reembolso ter sido calculado e aplicado não disparará um recálculo do pagamento de reembolso, e o método de pagamento selecionado no campo **Aplicar método de pagamento de créditos** não será aplicado. Se a opção **Aplicar crédito** precisar ser usada neste contexto, o usuário deverá excluir a ordem de substituição e a RMA e, depois, reiniciar e criar uma nova RMA. Desta vez, o usuário deve verificar se a opção **Aplicar crédito** está definida como **Sim** antes da execução da função **Concluir**.

## <a name="payment-overrides-for-call-center-returns"></a>Substituições de pagamento para devoluções de call center

Embora a lógica do call center determine sistematicamente o método de pagamento de reembolso da maneira descrita anteriormente neste tópico, os usuários às vezes podem desejar substituir esses pagamentos. Por exemplo, um usuário pode editar ou remover as linhas de pagamento de reembolso existentes e aplicar novas linhas de pagamento. Os pagamentos de reembolso calculados pelo sistema só podem ser alterados por usuários que tenham as permissões de substituição corretas. Essas permissões podem ser configuradas na página **Substituir permissões** no Retail e Commerce. Para fazer uma substituição de pagamento de reembolso, o usuário deve estar vinculado a uma função de segurança em que a opção **Permitir pagamento alternativo** está definida como **Sim** na página **Substituir permissões**.

![Opção Permitir pagamento alternativo na página Substituir permissões](media/overridepermissions.png)

Como alternativa, uma organização pode definir a opção **Permitir substituição de pagamento** como **Sim** na guia **RMA/devolução** da página **Parâmetros de call center**. Nesse caso, um código de substituição de segurança deve ser selecionado no campo **Código de Substituição de Segurança**. O código de substituição de segurança é um código alfanumérico que deve ser gerenciado externamente, pois os usuários não podem exibi-lo na sede do Commerce após defini-lo. O código de substituição de segurança deve ser conhecido por poucas pessoas confiáveis em uma organização. Quando a opção **Permitir substituição de pagamento** estiver definida como **Sim**, se algum usuário sem as permissões de função corretas tentar alterar o método de pagamento em uma ordem de devolução, ele terá a opção de inserir o código de substituição de segurança. Se ele não souber esse código ou se um gerente ou um supervisor não puder inseri-lo na página, ele não poderá substituir o método de pagamento de devolução.

> [!NOTE]
> Se o código de substituição de segurança for perdido ou esquecido, a organização precisará redefini-lo. Para isso, ela deverá definir um novo código de substituição de segurança no campo **Código de Substituição de Segurança** na guia **RMA/devolução** da página **Parâmetros de call center**.

![Parâmetros de substituição de pagamento na guia RMA/devolução da página Parâmetros de call center](media/overridepaymentparameter.png)

> [!IMPORTANT]
> Antes que as organizações tentem substituir os pagamentos de reembolso que usam tipos de pagamento por cartão de crédito, elas devem verificar se o processador de cartão de crédito permite reembolsos não vinculados. Muitos processadores exigem que os reembolsos sejam lançados novamente no cartão original. Qualquer tentativa de emitir um reembolso para um cartão sem capturas anteriores poderá causar falhas de lançamento com o processador.

## <a name="additional-resources"></a>Recursos adicionais

[Métodos de pagamento nos call centers](work-with-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]