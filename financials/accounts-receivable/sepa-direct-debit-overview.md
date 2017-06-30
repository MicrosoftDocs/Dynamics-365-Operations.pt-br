---
title: "visão geral do débito direto do SEPA"
description: "A Área Única de Pagamentos em Euros (SEPA) é configurada pela Comissão Europeia e dita que todos os pagamentos eletrônicos são considerados como domésticos, independentemente do país/região onde o indivíduo, a empresa ou a organização e o banco estão localizados. Não há diferença entre pagamentos nacionais e internacionais. A SEPA inclui os 28 países membros da União Europeia (EU), além de Islândia, Liechtenstein, Noruega, Suíça, Mônaco e São Marinho. A SEPA ajuda a formar um mercado único para transações de pagamento na Área Econômica Europeia (EEA). Por fim, espera-se que a SEPA reduza o número de formatos de pagamento com que bancos, empresas e indivíduos devem trabalhar."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 11144
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f3b20b033fc701204cbb3f62468a421b3bdd6a80
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="sepa-direct-debit-overview"></a>visão geral do débito direto do SEPA

[!include[banner](../includes/banner.md)]


A Área Única de Pagamentos em Euros (SEPA) é configurada pela Comissão Europeia e dita que todos os pagamentos eletrônicos são considerados como domésticos, independentemente do país/região onde o indivíduo, a empresa ou a organização e o banco estão localizados. Não há diferença entre pagamentos nacionais e internacionais. A SEPA inclui os 28 países membros da União Europeia (EU), além de Islândia, Liechtenstein, Noruega, Suíça, Mônaco e São Marinho. A SEPA ajuda a formar um mercado único para transações de pagamento na Área Econômica Europeia (EEA). Por fim, espera-se que a SEPA reduza o número de formatos de pagamento com que bancos, empresas e indivíduos devem trabalhar.   

<a name="what-is-the-goal-of-sepa-direct-debits"></a>Qual é o objetivo dos débitos diretos da SEPA?
---------------------------------------

Um débito direto da SEPA permite que um credor colete fundos da conta bancária de um cliente, desde que um mandato assinado tenha sido concedido pelo cliente ao credor. O cliente assina um mandato que autoriza o credor a cobrar um pagamento e instruir o banco do cliente a pagar a cobrança. 

Os débitos diretos da SEPA criar, pela primeira vez, um instrumento de pagamento que pode ser usado para débitos diretos nacionais ou internacionais em euro em todos os 32 países/regiões da SEPA. 

Existem dois esquemas disponíveis: o Esquema de Débito Direto Principal da SEPA e o Esquema de Débito Direto de B2B da SEPA. Ambos os esquemas usam o mesmo formato de arquivo.

## <a name="what-is-the-core-direct-debit-scheme"></a>O que é o esquema de Débito Direto Principal?
O Esquema de Débito Direto Principal da SEPA é o esquema básico. Tem os seguintes atributos:
-   A transferência de fundos é feita em euros (mesmo se as contas bancárias contiverem fundos em outras moedas).
-   O cliente e o credor devem, cada um, ter uma conta em uma instituição de crédito localizada na SEPA.
-   O cliente deve conceder um mandato assinado ao credor.
-   Os mandatos vencem 36 meses após a última cobrança iniciada.
-   O credor deve armazenar mandatos enquanto eles estiverem válidos e por pelo menos 14 meses após a última cobrança.
-   O esquema pode ser usado para uma cobrança única (uma vez) ou para cobranças de débito direto recorrentes.
-   Os clientes têm um direito "sem perguntas" de receber um reembolso em até oito semanas após o débito da conta.

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>O que é o esquema Débito Direto B2B da SEPA?
O Esquema de Débito Direto B2B da SEPA se aplica a transações business-to-business e se baseia no Esquema de Débito Direto Principal da SEPA. As diferenças principais são:
-   O Esquema de Débito Direto B2B da SEPA não será permitido quando o cliente for um indivíduo particular (cliente).
-   O cliente não está qualificado a obter um reembolso de uma transação autorizada.
-   Os bancos do cliente devem ter certeza de que a cobrança está autorizada, verificando a cobrança em relação às informações do mandato. Os bancos do cliente e os clientes devem concordar com o fato de que a verificação será executada para todos os débitos diretos.
-   O esquema oferece uma linha do tempo mais curta para apresentar débitos diretos e reduz o período de devolução.

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>Posso usar o esquema COR1 para cartas de ordem de débito direto?
Sim. Você pode usar o esquema COR1 para cartas da ordem de débito direto SEPA na Áustria, na Bélgica, na Alemanha, na França, na Itália, na Espanha e nos Países Baixos. O esquema oferece um período mais curto de pré-notificação para a coleta de débito direto do credor.

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>O que são os Números de Conta Bancária Internacional (IBAN) e os Códigos Identificadores Bancários (BIC)?
O Número de Conta Bancária Internacional (IBAN) e o Código Identificador Bancário (BIC) são usados para identificar todas as contas dos 32 países/regiões da SEPA. Insira o BIC no campo Código SWIFT e o IBAN no campo IBAN. Ambos os campos estão localizados na Guia Rápida Identificação adicional na guia Conta bancária na página Contas bancárias. Isso é verdadeiro para a conta bancária do credor e para a conta bancária do cliente.

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>Onde insiro os identificadores do credor (IDs de débito direto)?
Na SEPA, cada credor é identificado por um identificador do credor exclusivo. Esse identificador permite que o cliente e o banco do cliente filtrem cada débito direto e então processem ou rejeitem o débito direto de acordo com as instruções do cliente. Os credores devem solicitar esse identificador por meio de seus bancos. Insira esse identificador no campo ID de débito direto da conta bancária da entidade legal.

## <a name="what-are-mandates"></a>O que são mandatos?
O cliente assina um mandato que autoriza o credor a cobrar um pagamento e instruir o banco do cliente a pagar a cobrança. O cliente pode emitir o mandato em formulário de papel ou eletronicamente. Por padrão, o mandato vence 36 meses após a última vez em que o débito direto foi iniciado.

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>Onde eu especifico o formato de arquivo de Débito Direto da SEPA (ISO 20022)?
Os formatos de dados da SEPA se baseiam nos padrões de mensagem ISO 20022. Você marcará a caixa de seleção Relatório eletrônico genérico e selecionará o formato de débito direto de SEPA como uma configuração de formato de exportação ao configurar métodos de pagamento de contas a pagar. Use esse método de pagamento ao gerar um arquivo de pagamento em um diário de pagamentos do cliente.

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>Em quais formatos de arquivo posso gerar arquivos de pagamento de débito direito de SEPA?
Você pode gerar arquivos de pagamento eletrônico para os débitos diretos da SEPA nos seguintes formatos:
-   Arquivos de pagamento de débito direto da SEPA no formato de arquivo XML PAIN.008.001.02 para a Bélgica, a Alemanha, a Espanha, a França, a Itália e os Países Baixos.
-   Os arquivos de pagamento de débito direto da SEPA no formato de arquivo XML PAIN.008.001.02 para a Áustria e no formato de arquivo XML PAIN.008.003.02 para a Alemanha.

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>Como os reembolsos e devoluções funcionam com débitos diretos da SEPA?
Em ambos os esquemas de Débito Direto da SEPA, os clientes têm determinados direitos a reembolsos. O cliente pode cancelar todas as transações autorizadas durante um período de oito semanas após a data de vencimento, sem que seja necessário dar um motivo. No caso das transações não autorizadas, o período é estendido a 13 meses após a data de vencimento. Os estornos de todos os pagamentos feitos são executados manualmente usando o botão Cancelar pagamento na página Transações de cliente.






