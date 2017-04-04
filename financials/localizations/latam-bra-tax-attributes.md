---
title: Atributos de imposto para O Brasil
description: "Este tópico explica como configurar informações fiscais para destinatários, entidades, legais, clientes e fornecedores, e para o produto que são liberadas a uma entidade legal brasil. Essas informações são necessárias para o cálculo de imposto, e para as notas fiscais e outras instruções necessários que você envia os livros fiscais."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustTable, EcoResProductDetails, LogisticsAddressSetup
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269544
ms.assetid: 92b0cf1b-51ec-4611-bf8e-db4cd10ffed0
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 7bc0de6272bf3b985593fef6556e57516afa5baa
ms.lasthandoff: 03/31/2017


---

# <a name="tax-attributes-for-brazil"></a>Atributos de imposto para O Brasil

Este tópico explica como configurar informações fiscais para destinatários, entidades, legais, clientes e fornecedores, e para o produto que são liberadas a uma entidade legal brasil. Essas informações são necessárias para o cálculo de imposto, e para as notas fiscais e outras instruções necessários que você envia os livros fiscais.

<a name="tax-address-attributes"></a>Atributos do endereço de imposto
----------------------

Para qualquer pessoa jurídica que tenha um endereço em O Brasil, o código de Institute Brasileiro de Região e Estatística (IBGE) deve estar configurado o estado e/ou a cidade. O código de IBGE é usado para identificar a região em que o endereço está localizado, para que os impostos corretos sejam consideradas. Informações de IBGE vem de IBGE, que é uma organização que mapee oficial geografia brasil.

1.  ** Em configuração de endereço **, ** página no estado/província ** o campo grupo, em ** País/região ** campo, selecione ** BRA **. Em, ** código de IBGE ** no campo, insira o código de IBGE do estado.
2.  ** ** Cidade no campo grupo, em ** País/região ** campo, selecione ** BRA **. Em, ** código de IBGE ** no campo, insira o código de IBGE para a cidade.

## <a name="customer-tax-attributes"></a> Atributos de imposto do cliente
Os seguintes campos ** ** cliente na página são necessários para uma pessoa jurídica brasil.

| Campo                                                                   | descrição                                                                                                                                                                                                       |
|-------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CNPJ                                                                | Imposto - número de registro, o pagador ou Cadastro Nacional da Pessoa Jurídica (/Cadastro) CNPJ de Pessoas Físicas (CPF), a entidade legal.                                                                         |
| IE                                                                      | O número de registro do estado, ou Estadual (IE) registro, a entidade legal.                                                                                                                                   |
| CCM                                                                     | O número de registro ou municipais, Cadastro de contribuinte mobiliário (CCM), a entidade legal.                                                                                                             |
| NIT                                                                     | O número de identificação de trabalho.                                                                                                                                                                                 |
| \_CEI INSS                                                               | O número do brasil de segurança.                                                                                                                                                                                    |
| CNAE                                                                    | O código de classificação nacionais, ou Classificação nacionais de Atividades Econômicas (CNAE), para a atividade econômica de entidade legal.                                                                       |
| ID de estrangeiro                                                            | O número de identificação natural de país/região para clientes estrangeiros.                                                                                                                                                       |
| Serviço no endereço de entrega                                             | Quando esta opção é definida ** Sim **, códigos de serviço e o código de IBGE cidade do endereço de entrega será aplicado.                                                                                                   |
| ** SUFRAMA (SUFRAMA ** região do grupo de campos)                         | Define esta opção ** Sim ** se o cliente está está localizado a região do Superintendência da Zona Franca de Manaus (SUFRAMA) em O Brasil.                                                                                |
| Número do SUFRAMA ** (SUFRAMA ** região do grupo de campos)                  | Se o cliente está localizado a região de SUFRAMA, insira o número de registro do cliente. SUFRAMA                                                                                                      |
| Descontar PIS e COFINS                                                 | Se o cliente está localizado a região de SUFRAMA, definir Sim ** essa opção aplicar ** descontos aos impostos do Programa de Integração Social (PIS e de Contribuição para o Financiamento da Seguridade Social (COFINS). |
| Gerar a nota fiscal de entrada (** ** devolução de vendas no grupo de campos) | Definir Sim ** essa opção ** emitir a nota fiscal de entrada para devoluções de vendas quando o cliente não for uma empresa e não emitiu notas fiscais.                                                           |
| Usuário final                                                              | Se essa opção está definida ** Sim **, o cliente é o usuário final.                                                                                                                                                 |
| Contribuinte do ICMS                                                        | Se essa opção está definida ** Sim **, o cliente terá registro e deve cobrar imposto sobre Circulação de Mercadorias e o de Imposto ICMS ().                                                               |
| Tipo de atendimento                                                           | O tipo de ponto quando um documento é emitido fiscal ao cliente.                                                                                                                                            |

## <a name="vendor-tax-attributes"></a> Atributos de imposto do fornecedor
Os seguintes campos ** fornecedor ** o página são necessários para uma pessoa jurídica brasil.

| Campo                             | descrição                                                                                                                         |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| CNPJ                          | Imposto - insira número de registro de CNPJ/CPF pagador () a entidade legal.                                                             |
| IE                                | Insira o número de registro de IE estado () a entidade legal.                                                                       |
| CCM                               | Insira o número de registro (CCM municipal) a entidade legal.                                                                  |
| NIT                               | O número de identificação de trabalho.                                                                                                   |
| \_CEI INSS                         | O número do brasil de segurança.                                                                                                      |
| CNAE                              | Insira o código de classificação (natural CNAE) para a atividade econômica de entidade legal.                                        |
| ID de estrangeiro                      | O número de identificação natural de país/região de fornecedor, se o fornecedor for uma pessoa de outro país/região.                               |
| Gerar nota fiscal recebida | Definir Sim ** essa opção ** emitir a nota fiscal de entrada ao fornecedor não é uma empresa e não emitiu notas fiscais. |
| Uso e consumo               | Define esta opção se Sim ** ** produtos deste fornecedor destinam-se ser usados e consumido em qualquer processo.                        |
| Código de rendimento                       | O código usado em livros fiscais para identificar o código de receita do fornecedor.                                                    |
| Contribuinte do ICMS                  | Se essa opção está definida ** Sim **, o fornecedor tem o registro e deve cobrar impostos ICMS.                                        |
| Tipo de atendimento                     | O tipo de ponto quando uma nota fiscal é recebida do fornecedor.                                                                |
| Serviço no endereço de entrega       | Definir Sim ** essa opção aplicar ** códigos de serviço e o código da cidade de IBGE.                                                           |

## <a name="product-tax-attributes"></a> Atributos de imposto do produto
Os seguintes campos ** informações sobre produtos ** o página são necessários para uma pessoa jurídica brasil.

| Campo                                   | descrição                                                                        |
|-----------------------------------------|------------------------------------------------------------------------------------|
| Origem da tributação                         | A origem de produto da tributação com.                                   |
| Tipo de Produto                            | O tipo de produto. Este campo é usado para classificar o tipo de produto.           |
| Código de classificação fiscal              | O código de classificação fiscal.                                                    |
| Código de exceção                          | O código de exceções para imposto sobre Produtos Industrializados de sobre Impostos (IPI).          |
| Código de serviço                            | A classificação fiscal para um item de tipo serviço.                         |
| ICMS sobre serviço                         | Os impostos ICMS aplicados em um item de tipo serviço.                       |
| Aproxime a porcentagem (encargos fiscal) | A taxa de impostos usado para calcular o valor do imposto para o produto. |
| Código CEST (substituição tributária)            | O número de código usado se a substituição tributária é permitido para o item.          |




