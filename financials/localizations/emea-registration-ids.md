---
title: IDs de Registro
description: "Este tópico fornece informações sobre configuração e uso das IDs de registro."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264824
ms.assetid: e86f0a35-be58-4ef5-b5ab-bcfc495eaa13
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 32cd09975861083b8940368ed53ae16e89bcd748
ms.lasthandoff: 03/31/2017


---

# <a name="registration-ids"></a>IDs de Registro

Este tópico fornece informações sobre configuração e uso das IDs de registro.

Muitos países e regiões têm regulamentos e requisitos diferentes para registrar números de registro ou IDs. Este tópico fornece uma visão geral configurações necessários e o processamento do registro de suporte para os participantes de países europeus/regiões diferentes. Todos os países/regiões têm os requisitos de suportar várias país e funcionalidades específicas relacionadas aos números de registro são fornecidos pelo escritório de estado. Exemplos de números de registro são, número de CPF (SSN), número de identificação (TIN) de imposto, e identificação europeia de IVA (ID de IVA da UE.) Este recurso fornece a estrutura unificada para todos os países em todas as regiões que leva em consideração requisitos específicos de país e alguns países europeus. As seções a seguir descrevem as informações de circulação total usada configurando processando e IDs de registro.

## <a name="registration-type-creation"></a>Criação de tipos de registro
Antes que você possa inserir a ID de registro, você deve configurar tipos de registro para os diferentes tipos de números de registro que cada participante está sujeito a. Ir ** administração organizacional ** &gt; ** o catálogo de endereços global ** &gt; ** tipos de registro ** &gt; ** tipos de registro ** página para criar e gerenciar tipos de registro para fornecedores, clientes, funcionários, e legais em entidades diferentes países/regiões.

|Campo                 |descrição      |
|------------------------------|----------------------------|                                                                           
| Nome                | O nome do tipo de registro. |                                                                           
| descrição         | A descrição do tipo de registro. |
| País/região      | O identificador exclusivo do país/região.|
| Autoridade fiscal       | A autoridade de impostos associado ao tipo de registro.|
| Restrito a       | O tipo de restrição que se aplica ao tipo de registro de imposto: Nenhum, pessoa, organização.|
| Formatar              | O formato de validação para o tipo de registro.|
| Pode ser atualizado      | Define se o número do tipo de registro pode ser atualizado após será inserido.|
| Exclusivo              | Define se o número do tipo de registro é exclusivo. |
| Principal para o país/região | Se um participante estiver associado com o país de um ou vários endereços particularmente e a ID de registro será válido para todos esses endereços, deverá como designar um endereço principal para o país. Você só pode registrar um ID como principal. Define se o número de registro pode ser inserido somente para o endereço principal para o país. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Atribua um tipo de registro para uma categoria de registro
A categoria de registro for identificador do registro do país/região aprovado usando particularmente o país/região para impostos, alfândega e outras finalidades. Esta categoria definir regras de validação de ID de registro específico (incluindo os dígitos de cheque etc.) e da ID de registro da inclusão em diferentes relatórios. Use a página administração ** organizacional ** &gt; ** catálogo de endereços global ** &gt; ** tipos de registro ** &gt; ** categorias de registro ** atribuir o tipo de país específico a categoria suportado de registro.

| Campo            | descrição|
|-----------------------|----------------|
| Tipo de registro     | O país/região do tipo de registro em especial.|
| Restrito a         | O tipo de restrição se aplica ao tipo de registro de imposto: Nenhum, pessoa, organização.|
| Categoria de registro | O identificador exclusivo da registradora aprovado usando o país. A lista completa de suporte em categorias AX7.1 está abaixo. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Insira IDs de registro para registros de catálogo de endereços global
O catálogo de endereços global (GAB) no Microsoft Dynamics 365 para operações contém informações de endereço consolidada para clientes, fornecedores, contatos, parceiros comerciais, bem entidades legais. Para obter mais informações, consulte visão geral [] de catálogo de endereços global (/dynamics365/operations/organization-administration/overview-global-address-book). Os registros de participantes que são armazenados no catálogo de endereços global pode conter uma ou mais addresss record. Esses endereços são usados para fins diferentes, como o faturamento ou a entrega. Você pode configurar IDs de registro para informações de endereço para clientes, fornecedores, funcionários e órgãos, legais. Localizar a parte (a entidade legal, fornecedor, cliente, trabalhador) para que o registro que você deseja inserir a ID de registro, clique em registro de IDs ** ** os formulários relacionados para o participante, pessoa jurídica, fornecedor, cliente, para abrir trabalhador ** gerenciar endereços ** a página. ** Inscrição municipal ** na guia, clique em adicionar ** **, e insira estas informações sobre a ID de registro.

|Campo                |descrição                                                |
|---------------------|-----------------------------------------------------------|
| Tipo de registro   | O registro no país/região selecionados.     |
| Número de inscrição | A ID De registro de O participante.                                |
| descrição         | A descrição do número de registro.               |
| Seção             | Informações adicionais sobre o número de registro. |
| Agência emissora      | A autoridade que emitiu o número de registro.        |
| Data da emissão         | A data emitida para o número de registro.              |
| Efetivação           | A data de efetivação para o número de registro.           |
| Vencimento          | A data de vencimento para o número de registro.          |

> [!NOTE]
> O número de isenção de imposto de entidade legal, fornecedor, cliente pode ser selecionado de IDs de registros relacionados à ID de IVA e inseridos para o participante.

## <a name="search-for-records-by-registration-id"></a>Procure registros por ID de registro
Procure os registros do interessado com base em uma ID de registro está disponível nos formulários relacionados para o participante, a entidade legal, o fornecedor, o cliente, e o trabalhador. ** Clique em busca de ID de registro para abrir ** ** critérios de pesquisa da ID de registro ** a página. Especifique os critérios de pesquisa e clique em localizar ** **. Exibirá o sistema os registros selecionados de catálogo de endereços global e tipos associados de registro do participante.

## <a name="supported-registration-categories"></a>Suporte categorias de registro
A tabela a seguir lista o registro suportado no dynamics 365 para as operações. Se você estiver familiarizado com o Microsoft Dynamics AX 2012 de IDs de registro, esta tabela os campos também é mapeado o dynamics 365 para categorias de registro das operações.

| Dynamics 365 para a categoria de registro das operações         |País/Região  | Termo ou campo do dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| ID do IVA                                                        | Todos os países da União europeia (EU)|  Número de isenção de imposto (ID legislativo dos IMPOSTOS do tipo em AX2012 R3)|
| ID da empresa (COID)                                          | Suíça de Polônia Bélgica República tcheca Estônia Hungria Letónia Lituânia | Número de registro do número de empresa (EnterpriseNumber) (número de registro de RegNum W (\_) número de registro de RegNum W (\_) número de registro de RegNum W (\_) número de registro de código da empresa do\_RegNum W) (EnterpriseCode) (\_) RegNum W UID (tipo legislativo UID em AX2012 R3) |
| ID da unidade                                                     | Bélgica            | Número de matriz (BranchNumber)|
| Značka de Spisová (número de registro, emissão agência, seção) | República Tcheca     | Número do baixo-relevo () CommercialRegisterInsetNumber mantido na seção de registro (CommercialRegister comercial) de registro (CommercialRegisterSection comercial)|
| ID de cliente personalizada                                           | Finlândia | Número do cliente de CustomsCustomerNumber alfândega (\_) FI|
| INN                                                           | Federação Russa| INN (tipo legislativo em INN AX2012 R3)|
| RRC                                                           | Federação Russa| RRC (tipo legislativo em RRC AX2012 R3)|
| OKDP                                                          | Federação Russa| OKDP (tipo legislativo em OKDP AX2012 R3)|
| OKPO                                                          | Federação Russa| OKPO (tipo legislativo em OKPO AX2012 R3)|
| RCOAD                                                         | Federação Russa| RCOAD (tipo legislativo em RCOAD AX2012 R3)|
| OGRN                                                          | Federação Russa| OGRN (tipo legislativo em OGRN AX2012 R3) |
| SNILS                                                         | Federação Russa| SNILS (tipo legislativo em SNILS AX2012 R3)|
| CIFTS                                                         | Federação Russa| CIFTS (tipo legislativo em CIFTS AX2012 R3)|

Para obter mais informações sobre processar de IDs de registro, como pré-requisitos necessárias, consulte as seguintes registros de tarefa para a ID de IVA em serviços (LCS) do ciclo de vida:

-   Configurar ID do VAT
-   ID de registro de IVA do fornecedor
-    Pesquisa de participante usando ID VAT



