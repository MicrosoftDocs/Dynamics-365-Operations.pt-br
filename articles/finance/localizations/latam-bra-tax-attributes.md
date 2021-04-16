---
title: Atributos de impostos do Brasil
description: Este tópico explica como configurar informações fiscais para endereços, entidades legais, clientes e fornecedores, e para os produtos que são liberados para uma entidade legal do Brasil. Essas informações são necessárias para o cálculo de imposto, e para as notas fiscais e outras instruções necessárias que você envia dos livros fiscais.
author: sndray
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, EcoResProductDetails, LogisticsAddressSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 269544
ms.assetid: 92b0cf1b-51ec-4611-bf8e-db4cd10ffed0
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4ce71052961f9157839df4e8a9daa26c0cc74767
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826068"
---
# <a name="tax-attributes-for-brazil"></a>Atributos de impostos do Brasil

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar informações fiscais para endereços, entidades legais, clientes e fornecedores, e para os produtos que são liberados para uma entidade legal do Brasil. Essas informações são necessárias para o cálculo de imposto, e para as notas fiscais e outras instruções necessárias que você envia dos livros fiscais.

<a name="tax-address-attributes"></a>Atributos de endereço para imposto
----------------------

Para qualquer entidade legal que tenha um endereço no Brasil, o código do IBGE (Instituto Brasileiro de Geografia e Estatística) deve estar configurado no estado e/ou cidade. O código do IBGE é usado para identificar a região na qual o endereço está localizado, para que os impostos corretos sejam considerados. As informações do código IBGE vem do IBGE, que é uma organização oficial que mapeia a geografia brasileira.

1.  Na página **Configuração de endereço**, no grupo de campo **Estado/província**, no campo **País/região**, selecione **BRA**. Em seguida, no campo **código IBGE**, insira o código IBGE do estado.
2.  No grupo de campo **Cidade**, no campo **País/região**, selecione **BRA**. Em seguida, no campo **código IBGE**, insira o código IBGE da cidade.

## <a name="customer-tax-attributes"></a>Atributos de imposto do cliente
Os seguintes campos na página **Cliente** são necessários para a entidade legal brasileira.

| Campo                                                                   | descrição                                                                                                                                                                                                       |
|-------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CNPJ                                                                | O número de inscrição de contribuinte ou (CNPJ) Cadastro Nacional da Pessoa Jurídica/CPF (Cadastro de Pessoas Físicas) do fornecedor.                                                                         |
| IE                                                                      | O número de inscrição do estado ou IE (Inscrição Estadual) da entidade legal.                                                                                                                                   |
| CCM                                                                     | O número de registro municipal ou CCM (Cadastro de Contribuinte Mobiliário) da entidade legal.                                                                                                             |
| NIT                                                                     | O número de identificação do trabalhador.                                                                                                                                                                                 |
| INSS\_CEI                                                               | O número de segurança brasileiro.                                                                                                                                                                                    |
| CNAE                                                                    | O código de classificação nacional ou CNAE (Classificação Nacional de Atividades Econômicas), da atividade econômica da entidade legal.                                                                       |
| ID de estrangeiro                                                            | O número de identificação de país/região natural para clientes estrangeiros.                                                                                                                                                       |
| Serviço no endereço de entrega                                             | Quando esta opção é definida como **Sim**, os códigos de serviço e o código da cidade do IBGE do endereço de entrega são aplicados.                                                                                                   |
| SUFRAMA (No grupo de campo da **região da SUFRAMA**)                         | Defina esta opção como **Sim** se o cliente estiver localizado na região da Superintendência da Zona Franca de Manaus (SUFRAMA) no Brasil.                                                                                |
| Número da SUFRAMA (No grupo de campo da **região da SUFRAMA**)                  | Se o cliente estiver localizado na região de SUFRAMA, insira o número de registro SUFRAMA do cliente.                                                                                                      |
| Descontar PIS e COFINS                                                 | Se o cliente estiver localizado na região da SUFRAMA, defina esta opção como **Sim** para aplicar descontos aos impostos PIS (Programa de Integração Social) e COFINS (Contribuição para o Financiamento da Seguridade Social). |
| Gerar a nota fiscal de entrada (No grupo de campo **Devolução de venda**) | Defina esta opção como **Sim** para emitir a nota fiscal de entrada para devoluções de vendas quando o cliente não for uma empresa e não emitiu notas fiscais.                                                           |
| Usuário final                                                              | Se esta opção for definida como **Sim**, o cliente é o usuário final.                                                                                                                                                 |
| Contribuinte do ICMS                                                        | Se esta opção for definida como **Sim**, o cliente tem registro e deve pagar o ICMS (Imposto sobre Circulação de Mercadorias e Serviços).                                                               |
| Tipo de atendimento                                                           | O tipo de atendimento quando uma nota fiscal é emitida ao cliente.                                                                                                                                            |

## <a name="vendor-tax-attributes"></a>Atributos de imposto do fornecedor
Os campos a seguir na página **Fornecedor** são obrigatórios para a entidade legal brasileira.

| Campo                             | descrição                                                                                                                         |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| CNPJ                          | Insira número de inscrição de contribuinte (CNPJ/CPF) da entidade legal.                                                             |
| IE                                | Insira número de inscrição estadual (IE) da entidade legal.                                                                       |
| CCM                               | Insira número de inscrição municipal (CCM) da entidade legal.                                                                  |
| NIT                               | O número de identificação do trabalhador.                                                                                                   |
| INSS\_CEI                         | O número de segurança brasileiro.                                                                                                      |
| CNAE                              | Insira o código de classificação nacional (CNAE) da atividade econômica da entidade legal.                                        |
| ID de estrangeiro                      | O número de identificação natural de país/região de fornecedor, se o fornecedor for uma pessoa de outro país/região.                               |
| Gerar nota fiscal recebida | Defina esta opção como **Sim** para emitir a nota fiscal de entrada quando o fornecedor não for uma empresa e não emitir notas fiscais. |
| Uso e consumo               | Defina esta opção como **Sim** se os produtos deste fornecedor forem destinados para serem usados e consumidos em qualquer processo.                        |
| Código de rendimento                       | O código usado em livros fiscais para identificar o código de receita do fornecedor.                                                    |
| Contribuinte do ICMS                  | Se esta opção for definida como **Sim**, o fornecedor tem registro e deve pagar o ICMS.                                        |
| Tipo de atendimento                     | O tipo de atendimento quando uma nota fiscal é recebida do fornecedor.                                                                |
| Serviço no endereço de entrega       | Defina esta opção como **Sim** para aplicar os códigos de serviço e o código da cidade do IBGE.                                                           |

## <a name="product-tax-attributes"></a>Atributos de imposto do produto
Os seguintes campos na página **Informações sobre produtos** são necessários para a entidade legal brasileira.

| Campo                                   | descrição                                                                        |
|-----------------------------------------|------------------------------------------------------------------------------------|
| Origem da tributação                         | A origem de produto para fins de tributação.                                   |
| Tipo de Produto                            | O tipo de produto. Este campo é usado para classificar o tipo de produto.           |
| Código de classificação fiscal              | O código de classificação fiscal.                                                    |
| Código de exceção                          | O código de exceção para IPI (Imposto sobre Produtos Industrializados).          |
| Código de serviço                            | A classificação fiscal para um item do tipo de serviço.                         |
| ICMS sobre serviço                         | Os impostos ICMS aplicados em um item do tipo de serviço.                       |
| Percentual aproximado de imposto (Carga tributária) | A alíquota usada para calcular o valor aproximado do imposto do produto. |
| CEST (Código de substituição tributária)            | O código numérico usado se a substituição do imposto for permitida para o item.          |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]