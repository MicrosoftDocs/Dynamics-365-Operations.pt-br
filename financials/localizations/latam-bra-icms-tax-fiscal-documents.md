---
title: Notas fiscais de IMPOSTO ICMS para O Brasil
description: "Este tópico explica o conceito de notas fiscais de vendas e descreve os requisitos para gerá-los."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxFiscalDocument_BR, TaxFiscalDocumentCancel_BR, TaxFiscalDocumentListPage_BR, TaxFiscalDocumentPost_BR
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269524
ms.assetid: 6960c023-1e50-42b7-82a5-4603dd35fa6d
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 21a0ab010fabeb8fef647b11ece561d5e6b86044
ms.lasthandoff: 03/31/2017


---

# <a name="icms-tax-fiscal-documents-for-brazil"></a>Notas fiscais de IMPOSTO ICMS para O Brasil

Este tópico explica o conceito de notas fiscais de vendas e descreve os requisitos para gerá-los.

Em O Brasil, alguns tipos de notas fiscais não têm efeito sobre fornecedores, em clientes, ou nos saldos de estoque. Normalmente, a finalidade das notas fiscais é habilitar entidades legais para especificar ajustes de impostos para transferi-las, entre outros, subsidiárias ou de onde recuperar impostos (recebíveis impostos) em prestações para um período. Para registrar essas operações na entidade legal, as notas fiscais específicos devem ser produzidos que afetam a contabilidade e relatórios de livros fiscais.

## <a name="imposto-sobre-circulao-de-mercadorias-e-servios-icms-tax-transfers-between-subsidiaries"></a>Transferências do imposto sobre Circulação de Mercadorias e o de Imposto ICMS (entre subsidiárias)
Este tipo de impostos é considerado um imposto recuperáveis e as regulamentações de imposto de renda corporativo não permitem que os impostos ICMS são deduzidos. Portanto, os créditos acumulados ICMS não podem ser usados para diminuir o valor tributável para avaliação de imposto sobre rendimento corporativos (IRPJ e CSSL). Os modos de acumular créditos de ICMS incluem:

-   Exportação – de isenção de imposto ICMS
-   Diferimentos
-   Reduzida taxa
-   Créditos presumidos

Há várias opções para o gerenciamento dos créditos acumulados ICMS são usados quando o saldo devido resultante é maior de crédito acumulado débito. O crédito de imposto ICMS acumulado pode ser transferido nestas situações:

-   Transferir o crédito de ICMS para outras subsidiárias com o maior volume de transações que o ICMS vence. Isso se aplica apenas às subsidiárias localizados no estado.
-   Transferir o crédito de ICMS para pagar contas de fornecedor em operações de compra por material bruto e secundário, os pacotes de equipamento e, por um equipamento industrial.
-   Transferir o crédito de ICMS para outras subsidiárias. Até as 30 por cento de cada ativo fixo a operação do ativo que é direcionada para ativos fixos permanentes podem ser transferidas.
-   Pagamento de aquisição de chassi do caminhão novo mecanismo, com ou combustível, feito por estabelecimento rodoviário de transporte.
-   Transferir o crédito de ICMS de uma empresa que fabrique álcool etílico a empresa que cooperativa centraliza vendas. Até 30 dos impostos sobre vendas cobrados na remessa desse produto podem ser transferidas.
-   Transferir o crédito de ICMS para o estabelecimento industrial de óleo bruto.

Nessas situações, o valor que uma empresa que pode ser acumulado de imposto ICMS depende de regras específicas liquidadas pelo governo. O valor não é aplicável sempre a 100 do valor acumulado de IMPOSTO ICMS. Os créditos de ICMS são transferidos emitir uma nota fiscal que é conhecido como um documento fiscal de imposto. Esse documento deve incluir informações específicas que reflete a operação. O TIN possível emitir um eletrônica de nota fiscal de nota fiscal eletrônica (NF-e) transferir o crédito de imposto ICMS acumulado de outra subsidiária.

## <a name="recovering-icms-tax-in-installments"></a>Recuperando impostos ICMS em prestações
De acordo com a lei brasileira nenhum 102/2000, no 1º de janeiro de 2001, os créditos de ICMS decorrentes de compra ativos fixos usados especificamente em atividades relacionadas tributação de ICMS 1/48 podem ser valores por mês. Portanto, o crédito de ICMS não puder ser totalmente recuperado quando registros de usuário a compra. Em vez disso, o crédito de ICMS será recuperado em prestações 48 pelo tempo. Veja a seguir um exemplo:

-   Valor de aquisição de ativo: R$ 100.000, 00
-   Valor dos impostos ICMS: R$ 12.000, 00
-   Cálculo de IVA recuperável com a finalidade de distribuição em contas de ativos atuais e de longo prazo receber:
    -   Ativos atuais:
        1.  R$ 12.000, 00 ÷ 48 meses = R$ 250,00
        2.  R$ 250,00 × de 12 meses (1 ano) = R$ 3.000, 00
    -   Ativo de longo prazo:
        1.  R$ 12.000, 00 ÷ 48 meses = R$ 250,00
        2.  R$ 250,00 × de 36 meses (1 ano) = R$ 9.000, 00

No Microsoft Dynamics 365 para operações, as entradas serão os seguintes:

** Compra - ativa ** ** dinâmica fixa de 365 para operações: Nota fiscal de compra de ativo de recebimento **

** Ajuste de imposto ICMS ano ** ** dynamics 365 para operações: Voucher manual de diário ** ** (R$ 12.000, 00/48) prestações \* 12 (meses) **

ICMS recuperável ** prazo ** (conta diferida)

*R$ 12.000, 00 D*

ICMS recuperável ** curto prazo ** (conta diferida)

R$ 3.000, 00 D

Ativo Fixo

R$ 88.000, 00 C

Recoverable ICMS long term (deferred account)

*R$ C* 3.000, 00

** Ativo longo prazo (** adiada conta de saldo): R$ 9.000, 00

** Ajuste de imposto ICMS de mês ** ** dynamics 365 para operações: Emitir uma nota fiscal de imposto de entrada **

Conta de imposto recuperável ICMS

D DE R$ 250,00

Recoverable ICMS short term (deferred account)

*R$ C* 250,00

** Todos afeta ** notas fiscais na página, você pode fazer o seguinte:

-   Crie e lance uma nota fiscal de IMPOSTO ICMS para transferir o valor de IMPOSTO ICMS a um cliente ou fornecedor, ou de onde recuperar o valor dos impostos ICMS em prestações para compra de ativos fixos por uma entidade legal.
-   Adicionar texto da nota fiscal a uma nota fiscal de transferência ou apropriação de imposto ICMS.
-   Exiba as transações de comprovante que são relacionados a um documento fiscal de IMPOSTO ICMS ** ** transações de comprovante na página.
-   Cancelar uma nota fiscal de transferência ou apropriação de imposto ICMS lançada e gerar uma transação de comprovante cancelada. O valor da nota fiscal da transação do comprovante cancelado é o mesmo que o valor de nota fiscal original, mas o valor de faturamento for negativo.
-   Lance a nota fiscal e exiba cancelada, o original e as transações de comprovante canceladas ** ** transações de comprovante na página.
-   Imprimir um documento fiscal de IMPOSTO ICMS contabilidade. O texto de rodapé configurado ** configuração de gerenciamento de impressão em ** página não serão impressos em notas fiscais de IMPOSTO ICMS.

Quando um documento fiscal novo de impostos é criado, as seguintes opções estão disponíveis:

-   Transferência de imposto ICMS
-   Serviço de ICMS para utilizar crédito de ativos das correções (CIAP)

## <a name="prerequisites"></a>Pré-requisitos
Os seguintes pré-requisitos devem ser configurados para criar e lançar notas fiscais de imposto. Os parâmetros determinam como os dados serão exibidos em notas fiscais, e todas são necessárias. Parâmetros ausentes podem causar inconsistências ou validações incorretas durante o processo de postagem.

-   ** Brasileiros parâmetros: ** Defina o item, além ** ** ** PIS e COFINS ** os códigos de impostos usado para esses tipos de notas fiscais.
-   ** Grupos de postagem do razão em contabilização **: ** Definir condições curtos ** imposto a receber da conta contábil.

## <a name="example"></a>Exemplo
** Notas fiscais de saída **

-   Saída de documento fiscal para transferência de crédito de ICMS para outras entidades legais, matriz/subsidiária a mesma empresa/organização destinadas para a compensação do saldo de débito de ICMS (CFOP: 5.601 e 5.602)

** Notas fiscais de entrada **

-   Notas fiscais de entrada para transferência de crédito de ICMS de outras entidades legais, subsidiárias e afiliadas a mesma empresa/organização destinadas para a compensação do saldo de débito de ICMS (CFOP: 1.601 e 1.602)
-   Notas fiscais de entrada para utilizar 1/48 de crédito de ICMS (CFOP: (1.604)) CIAP



