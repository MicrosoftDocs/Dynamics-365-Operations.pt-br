---
title: Integração e documentos fiscais CF-e com a funcionalidade de SAT no PDV do Commerce para o Brasil
description: Este tópico fornece uma visão geral da geração de documentos fiscais eletrônicos CF-e para vendas de varejo e seu registro na funcionalidade de dispositivo fiscal SAT no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.
author: akviklis
manager: annbe
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: akviklis
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4e3c082f7d29f90f04f4cadf5ba64bee4f4a7d7f
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408106"
---
# <a name="cf-e-fiscal-documents-and-integration-with-sat-functionality-in-commerce-pos-for-brazil"></a>Integração e documentos fiscais CF-e com a funcionalidade de SAT no PDV do Commerce para o Brasil

[!include[banner](../includes/banner.md)]

Este tópico fornece uma visão geral dos documentos fiscais CF-e (Cupom Fiscal eletrônico) e seu registro na funcionalidade de dispositivo fiscal SAT (Sistema Autenticador e Transmissor de Cupons Fiscais Eletrônicos) no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil. Ele também explica como emitir documentos CF-e e imprimir recibos fiscais CF-e-SAT (Cupom Fiscal Eletrônico - SAT) quando as vendas de mercadorias no varejo são concluídas no PDV do Commerce para o Brasil.

Um CF-e é um documento fiscal eletrônico gerado para registrar a venda de mercadorias para um cliente no estado de São Paulo. Ela permite o controle fiscal e fiscal por parte das autoridades fiscais. Ela também permite que os clientes verifiquem a validade e autenticidade dos documentos fiscais que recebem. As vendas de serviços não são compatíveis.

A funcionalidade do Commerce para o Brasil permite o formato CF-e modelo 59 para varejistas brasileiros. O formato CF-e modelo 59 é um padrão para as notas fiscais eletrônicas de varejo dentro das fronteiras do estado de São Paulo, juntamente com o formato NFC-e modelo 65 (Nota Fiscal do Consumidor eletrônica) do padrão nacional. Para obter mais informações sobre o formato NCF-e, consulte [Funcionalidade de documento fiscal NFC-e no PDV do Commerce para o Brasil](latam-bra-nfce.md).

O registro de documentos fiscais eletrônicos para vendas de varejo em um dispositivo SAT integrado é um dos métodos de registro fiscal disponíveis para varejistas no estado de São Paulo. Este recurso inclui a geração de documentos fiscais eletrônicos CF-e (formato CF-e modelo 59) para transações de vendas no PDV e o registro das documentos fiscais eletrônicos em um dispositivo fiscal SAT. Para obter mais informações, consulte [Sobre SAT](https://portal.fazenda.sp.gov.br/servicos/sat).

## <a name="feature-details"></a>Detalhes do recurso

O recurso de registro de documentos fiscais eletrônicos para vendas de varejo em um dispositivo SAT integrado permite o registro fiscal de vendas de varejo em um dispositivo SAT conectado a uma estação de hardware. O recurso aproveita a [estrutura de integração fiscal](../localizations/fiscal-integration-for-retail-channel.md). Portanto, ele oferece suporte a todos os recursos internos de integração fiscal. O recurso está incluído na solução pronta, mas deve ser configurado para que possa ser usado.

A geração de documentos fiscais eletrônicos CF-e (formato CF-e modelo 59) baseia-se em uma configuração de [Relatório eletrônico](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md) e é feita pelo mecanismo de tempo de execução de relatório eletrônico que faz parte do Commerce Runtime.

No momento, o recurso não oferece suporte a ordens do cliente que são retiradas no PDV. O suporte para a operação de retirada de ordem do cliente será adicionado posteriormente.

## <a name="supported-scenarios"></a>Cenários com suporte

Os cenários de exemplo a seguir mostram as ações do Commerce frequentemente realizadas que estão associadas a documentos CF-e-SAT.

### <a name="scenario-1-make-a-cash-and-carry-sale-of-goods-and-print-a-cf-e-sat-receipt"></a>Cenário 1: Fazer uma venda de mercadorias cash-and-carry e imprimir um recibo CF-e-SAT

1. Entre no POS.
1. Adicione produtos ao carrinho.
1. Registre os pagamentos da transação.
1. Selecione o formato CF-e-SAT (**Simplificado** ou **Detalhado**) e, em seguida, finalize a transação.
1. Verifique se as informações (incluindo o código de barras e o código QR) no recibo CF-e-SAT impresso correspondem à venda.

### <a name="scenario-2-make-a-cash-and-carry-sale-of-goods-to-an-identified-customer"></a>Cenário 2: fazer uma venda de mercadorias cash-and-carry para um cliente identificado

1. Entre no POS.
1. Adicione produtos ao carrinho.
1. Adicione um cliente nomeado ou insira manualmente informações do cliente. Para obter mais informações, consulte [Gerenciar informações de clientes no PDV para o Brasil](latam-bra-customer-information.md).
1. Registre os pagamentos da transação.
1. Selecione o formato CF-e-SAT (**Simplificado** ou **Detalhado**) e, em seguida, finalize a transação.
1. Verifique se as informações (incluindo o código de barras e o código QR) no recibo CF-e-SAT impresso correspondem à venda.

### <a name="scenario-3-initiate-a-cancellation-of-sold-goods"></a>Cenário 3: iniciar o cancelamento de mercadorias vendidas

Para cancelar uma venda, siga estas etapas.

1. Entre no POS.
1. Abra a página **Exibir diário**.
1. Encontre a venda que deve ser cancelada.
1. Selecione **Cancelar transação**.
1. Registre os reembolsos de pagamento da transação e, em seguida, finalize a transação.
1. Verifique se as informações (incluindo o código de barras e o código QR) no recibo CF-e-SAT de cancelamento impresso correspondem à transação.

> [!NOTE]
> O cancelamento de documentos CF-e aprovados que são emitidos por outras lojas não é compatível. Somente documentos CF-e que são emitidos pela mesma loja podem ser cancelados.

### <a name="scenario-4-make-a-cash-and-carry-sale-of-goods-by-using-sat-as-contingency-mode"></a>Cenário 4: Fazer uma venda de mercadorias por cash-and-carry usando SAT como modo de contingência

Se NFC-e for escolhido como um modo principal de um estabelecimento comercial no estado de São Paulo, o PDV deverá gerar documentos CF-e por meio de um dispositivo SAT quando a conexão com a Internet da loja não estiver disponível ou quando o serviço de autorização da SEFAZ (Secretaria de Estado de Fazenda) estiver inoperante. Esse uso de SAT é considerado um modo de contingência.

1. Entre no POS.
1. Adicione produtos ao carrinho.
1. Registre os pagamentos da transação. Você receberá um erro quando o PDV tentar se comunicar com a SEFAZ.
1. Selecione **Adiar** e, em seguida, finalize a transação.
1. Verifique se as informações (incluindo o código de barras e o código QR) no recibo CF-e-SAT impresso correspondem à venda.

### <a name="scenario-5-make-a-mixed-sale-that-contains-gift-cards-and-other-goods-in-the-same-transaction"></a>Cenário 5: fazer uma venda mista que contenha vales-presente e outras mercadorias na mesma transação

As operações de emissão de vales-presente e agregação de valor aos vales-presente não estão sujeitas a tributações no Brasil. Portanto, elas não são inseridas no recibo fiscal.

1. Entre no POS.
1. Adicione produtos ao carrinho.
1. Emita vales-presente na mesma transação.
1. Registre os pagamentos da transação.
1. Selecione o formato CF-e-SAT (**Simplificado** ou **Detalhado**) e, em seguida, finalize a transação.
1. Verifique se o recibo CF-e-SAT impresso não inclui os vales-presente junto com os outras mercadorias que foram vendidas.
1. Verifique se os recibos separados são impressos para cada vale-presente que foi vendido.

## <a name="custom-fields-for-cf-e-sat-fiscal-receipts"></a>Campos personalizados para recibos fiscais CF-e-SAT

Além dos campos descritos na [Lista comum de campos personalizados para DANFE](latam-bra-nfce.md#custom-fields-for-danfe-fiscal-receipts) e [DANFE simplificado para o recibo fiscal modelo 55](latam-bra-nfce-cancel-return.md#simplified-danfe-for-model-55-fiscal-receipt), um CF-e-SAT para recibo fiscal modelo 59 pode incluir os campos personalizados descritos nesta seção.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurar campos personalizados para que possam ser usados em formatos de recibos de vendas

Adicione os seguintes rótulos de PDV à seção **PDV** da página **Texto do idioma**.

| ID do Idioma | ID do texto | Texto                                            |
|-------------|---------|-------------------------------------------------|
| pt-BR       | 900201  | Nome comercial do emissor                             |
| pt-BR       | 900202  | Ambiente de teste                             |
| pt-BR       | 900203  | Ambiente de teste (">" caracteres em 3 linhas) |
| pt-BR       | 900204  | Valor total do cancelamento                        |
| pt-BR       | 900205  | Chave de acesso do cancelamento                         |
| pt-BR       | 900206  | Código QR do cancelamento                            |
| pt-BR       | 900207  | Código de barras do cancelamento (44 caracteres)            |
| pt-BR       | 900208  | Bloco 1 do código de barras do cancelamento (22 caracteres)    |
| pt-BR       | 900209  | Bloco 2 do código de barras do cancelamento (22 caracteres)    |
| pt-BR       | 900210  | Data de emissão do cancelamento                      |

Na página **Campos personalizados**, adicione os seguintes registros para os campos personalizados nos layouts de recibo. Observe que os valores de **ID de texto da legenda** devem corresponder aos valores de **ID de texto** especificados na página **Texto do idioma**.

| Nome                                                | Tipo    | ID do texto da legenda |
|-----------------------------------------------------|---------|-----------------|
| FISCALDOCUMENTESTABLISHMENTTRADENAME\_BR            | Recebimento | 900201          |
| EFDADDITIONALFISCALMESSAGETESTINGENVIRONMENT\_BR    | Recebimento | 900202          |
| EFDADDITIONALFISCALMESSAGETESTINGENVIRONMENTROW\_BR | Recebimento | 900203          |
| CANCELFISCALDOCUMENTTOTALAMOUNT\_BR                 | Recebimento | 900204          |
| CANCELFISCALDOCUMENTACCESSKEY\_BR                   | Recebimento | 900205          |
| CANCELFISCALDOCUMENTQRCODETEXT\_BR                  | Recebimento | 900206          |
| CANCELBARCODE\_BR                                   | Recebimento | 900207          |
| CANCELFISCALDOCUMENTBARCODEFIRST\_BR                | Recebimento | 900208          |
| CANCELFISCALDOCUMENTBARCODESECOND\_BR               | Recebimento | 900209          |
| CANCELFISCALDOCUMENTISSUEDATE\_BR                   | Recebimento | 900210          |

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo necessário, altere o valor do campo **Comportamento de impressão** para **Sempre imprimir**.

No designer de formato de recibo, adicione os seguintes campos personalizados às seções de recibo apropriadas. Observe que os nomes de campo correspondem aos valores de texto do idioma que você definiu na seção anterior.

- **Cabeçalho:** Adicione os seguintes campos:

    - **Nome comercial (Nome fantasia)** – O nome comercial do estabelecimento fiscal.
    - **Ambiente de teste (SAT em condição de teste)** – O texto "=&nbsp;TESTE&nbsp;=&nbsp;" e três linhas de colchetes angulares para a direita (\>), para casos em que o SAT está em condição de teste.
    - **Data de emissão do cancelamento (Emissão / Dados de recebimento)** – A data e hora em que o recibo de cancelamento é emitido.
    
- **Linhas:** Adicione os seguintes campos:
    
    - **Valor total do cancelamento (Valor total)** – O valor total do recibo de cancelamento.
    - **Chave de acesso do cancelamento (Chave de acesso)** – A chave de acesso do recibo de cancelamento.

- **Rodapé:** Adicione os seguintes campos:

    - **Código de barras** – Você pode adicionar um campo de código de barras ao CF-e-SAT para recibos fiscais modelo 59 para vendas. Esse código de barras é uma representação gráfica do valor da **Chave de acesso** de 44 dígitos.
    - **Bloco 1 do código de barras**, **Bloco 2 do código de barras** – Você pode adicionar campos de código de barras de 22 dígitos ao CF-e-SAT para recibos fiscais modelo 59 para vendas que são impressos em papel de recibo. Esse código de barras é uma representação gráfica do valor da **Chave de acesso** que é dividido em duas partes, cada uma com 22 dígitos.
    - **Código QR do cancelamento** – Um recibo pode incluir um código QR para o CF-e-SAT modelo 59 para cancelamentos, referindo-se à venda cancelada.
    - **Código de barras do cancelamento** – Um recibo pode incluir um código de varras para o CF-e-SAT modelo 59 para cancelamentos de vendas. Esse código de barras é uma representação gráfica do valor da **Chave de acesso do cancelamento (Chave de acesso)** de 44 dígitos.
    - **Bloco 1 do código de barras do cancelamento**, **Bloco 2 do código de barras do cancelamento** – Você pode adicionar campos de código de barras de 22 dígitos ao CF-e-SAT para recibos fiscais modelo 59 para cancelamentos de vendas que são impressos em papel de recibo. Esse código de barras é uma representação gráfica do valor da **Chave de acesso** que é dividido em duas partes, cada uma com 22 dígitos.

Para mais informações sobre como trabalhar com formatos de recibo, consulte [Configurar e criar formatos de recibo](../receipt-templates-printing.md).

## <a name="additional-resources"></a>Recursos adicionais

[Sobre SAT](https://portal.fazenda.sp.gov.br/servicos/sat)

[Configurar e implantar a localização do Commerce para o Brasil](latam-bra-deployment.md)

[Localização do Commerce para o Brasil](latam-bra-commerce-localization.md)

[Gerenciar informações do cliente no PDV para o Brasil](latam-bra-customer-information.md)

[Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil](latam-bra-nfce-cancel-return.md)

[Registro adiado de notas NFC-e emitidas no modo de contingência offline](latam-bra-nfce-contingency-mode.md)

[Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce](latam-bra-retail-statements.md)

[Configurar e criar formatos de recibo](../receipt-templates-printing.md)
