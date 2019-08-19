---
title: Restituição do IVA no gerenciamento de despesas
description: Este tópico explica como receber reembolsos em transações de IVA (imposto sobre valor agregado) qualificadas.
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70a53282bf1d140cb24108fe98e48aa82f783be5
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2019
ms.locfileid: "1795139"
---
# <a name="vat-recovery-in-expense-management"></a>Restituição do IVA no gerenciamento de despesas

[!include [banner](../includes/banner.md)]

Para receber reembolsos em transações de IVA (imposto sobre valor agregado) qualificadas, a empresa ou organização deve identificar, coletar, verificar e enviar informações precisas. Esse processo inclui várias tarefas e, dependendo do tamanho da empresa, pode incluir vários funcionários ou funções.

Para restituir o IVA usando o gerenciamento de despesas, os seguintes pré-requisitos devem ser concluídos:

- Códigos de imposto devem ser criados para os países/regiões alocados a categorias de despesas.
- Um grupo de imposto deve ser criado para cada código de imposto.
- Um código de imposto do item deve ser criado para cada grupo de imposto.

Depois que os pré-requisitos são concluídos, os funcionários seguem estas etapas para solicitar reembolsos de transações de IVA.

1. Em um relatório de despesas, inserem as informações fiscais sobre transações de cartão de crédito para identificar os reembolsos de IVA qualificados.
2. Verificam se todas as informações fiscais estão completas e, em seguida, lançam o relatório de despesas.
3. Processam despesas qualificadas para restituição de IVA internacional.
4. Enviar os dados de restituição de IVA para o outro fornecedor arquivar devoluções de restituição internacional.
5. Processar despesas para restituição de IVA doméstica.

As seções a seguir fornecem exemplos que mostram como os funcionários da Contoso concluem cada etapa.

## <a name="on-an-expense-report-enter-tax-information-about-credit-card-transactions-to-identify-eligible-vat-refunds"></a>Em um relatório de despesas, inserem as informações fiscais sobre transações de cartão de crédito para identificar os reembolsos de IVA qualificados

Nancy, representante de vendas da Contoso residente nos EUA, voltou recentemente de uma viagem de vendas para o Reino Unido. Durante a viagem, ela incorreu algumas despesas pessoais no cartão de crédito para refeições. Agora Nancy deve criar um relatório de despesas para reconciliar suas despesas.

Quando Nancy insere informações no relatório de despesas, ela seleciona **Reino Unido** no campo **País/região** na página **Editar relatório de despesas**. Em seguida, a lista de grupos de impostos é filtrada para mostrar apenas os grupos que se aplicam ao Reino Unido. Nancy seleciona o grupo de impostos **Reino Unido 001** e, em seguida, seleciona o grupo de impostos do item **Refeições**. Em seguida, ela adiciona uma nova transação para sua hospedagem. Como há somente um grupo de impostos e um grupo de impostos do item para hospedagem no Reino Unido, essa informação é preenchida automaticamente no relatório de despesas de Nancy.

Pela política da Contoso, todas as despesas devem ter um recibo correspondente. Portanto, quando Nancy salva o relatório de despesas, recebe uma mensagem informando que ela deve anexar um recibo para cada transação listada no relatório de despesas. Nancy verifica se anexou uma imagem digital de cada recibo de transação ao relatório de despesas e, em seguida, envia seu relatório para aprovação. Então, ela envia os recibos em papel para a equipe de processamento do back office. Essa equipe enviará os dados de restituição de IVA ao outro fornecedor que arquiva os reembolsos de restituição de IVA internacional para a Contoso.

## <a name="make-sure-that-all-tax-information-is-complete-and-then-post-the-expense-report"></a>Verificam se todas as informações fiscais estão completas e, em seguida, lançam o relatório de despesas

April, coordenadora de contas a pagar da Contoso, deve inserir todas as informações fiscais que estejam faltando em um relatório de despesas para que ele possa ser lançado. Ela abre a página **Detalhes de relatório de despesas** e vê o relatório de despesas aprovado de Nancy. Em seguida, April abre o relatório de despesas para ver os detalhes das transações. Ela vê que Nancy não especificou um grupo de imposto do item para uma das transações. Como essa informação não foi fornecida, April não pode lançar o relatório de despesas. Portanto, April verifica a página **Configurações de imposto** no gerenciamento de despesas, e localiza o grupo de imposto do item adequado para o país/região e o tipo de transação. Agora April pode lançar o relatório de despesas na contabilidade.

Quando April lança o relatório de despesas, um item de trabalho de restituição de IVA é criado. Esse item de trabalho é atribuído a um membro da equipe de processamento do back office. April recebe uma mensagem confirmando que o lançamento foi bem-sucedido. Essa mensagem também lista o número de transações de IVA que foram identificadas para restituição.

## <a name="process-expenses-that-are-eligible-for-international-vat-recovery"></a>Processam despesas qualificadas para restituição de IVA internacional

Arnie, membro da equipe de processamento do back office da Contoso, é responsável por confirmar que todas as informações necessárias para a restituição de IVA constem nos relatórios de despesas. Ele abre a página **Restituição de imposto de despesa** e seleciona o relatório de despesas que Nancy enviou. Arnie verifica se todos os recibos necessários estão anexados e se o grupo de impostos e os códigos de imposto do item corretos foram especificados.

Quando Arnie recebe os recibos em papel de Nancy, ele compara esses recibos com os recibos digitalizados e, em seguida, altera o status do relatório de despesas para **Pronto para recuperação**.

## <a name="send-vat-recovery-data-to-the-third-party-vendor-to-file-international-recovery-returns"></a>Enviar os dados de restituição de IVA para o outro fornecedor arquivar devoluções de restituição internacional

Quando Arnie está pronto para enviar os dados do relatório de despesas ao outro fornecedor que arquivará as devoluções de restituição de IVA, ele abre a página **Restituição de imposto de despesa**. Ele filtra a página para mostrar apenas os relatórios de despesas marcados como **Pronto para recuperação**. Em seguida, Arnie seleciona **Arquivo** &gt; **Exportar para Excel** As informações de IVA dos relatórios de despesas são exportadas para uma planilha do Microsoft Excel. Arnie envia essa planilha ao outro fornecedor e inclui uma mensagem informando que os recibos em papel foram enviados por mensageiro.

## <a name="process-expenses-for-domestic-vat-recovery"></a>Processar despesas para restituição de IVA doméstica

Arnie deve verificar se as transações dos relatórios de despesas estão qualificadas para restituição de IVA e se os recibos digitalizados estão anexados aos relatórios. Para começar a processar as despesas qualificadas para restituição doméstica, Arnie abre a página **Restituição de imposto de despesa** e seleciona o relatório de despesas que exige verificação. Ele verifica se os recibos estão no nome da empresa em vez do funcionário. Para restituição de IVA, os recibos devem estar no nome da empresa. Em seguida, Arnie confirma que o grupo de imposto e os códigos de imposto do item corretos foram aplicados.

Quando Arnie recebe os recibos em papel, ele altera o status do relatório de despesas para **Pronto para recuperação**. Assim, ele pode arquivar a devolução com a autoridade fiscal apropriada. Nesse caso, a autoridade fiscal apropriada nos EUA é a Administração Fiscal (IRS).
