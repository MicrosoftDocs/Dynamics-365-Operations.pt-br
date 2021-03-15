---
title: IDs de Registro
description: Este tópico fornece informações sobre configuração e uso das IDs de registro.
author: ShylaThompson
manager: AnnBe
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.reviewer: kfend
ms.custom: 264824
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: def0b35043f0a660e2a167b78cf0c65cd1e8b2fd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006025"
---
# <a name="registration-ids"></a>IDs de Registro

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre configuração e uso das IDs de registro.

Muitos países e regiões possuem requisitos e regulamentações diferentes para registrar números de inscrição ou IDs. Este tópico fornece uma visão geral das configurações necessárias e o processamento de tipos de registro suportados para os participantes de países/regiões diferentes da Europa. Todos os países/regiões têm os requisitos de suporte a várias funcionalidades específicas do país relacionadas aos números de registro fornecidos pelos diferentes órgãos estaduais. Os exemplos de números de registro incluem, Cadastro de Pessoas Físicas (CPF), Número de Identificação do Imposto (TIN) e Identificação europeia de IVA (ID de IVA da UE). Este recurso fornece a estrutura unificada para todos os países em todas as regiões, considerando requisitos específicos de país e de alguns países europeus. As seções a seguir descrevem o fluxo geral de informações usadas para configurar e processar IDs de registro.

## <a name="registration-type-creation"></a>Criação de tipos de registro
Antes de inserir a ID de registro, é necessário configurar os tipos de registros para os diferentes tipos de números de registro ao qual cada participante está sujeito. Vá até a página **Administração da organização** &gt; **Catálogo de endereços global** &gt; **Tipos de registro** &gt; **Tipos de registro**  para criar e gerenciar tipos de registros para fornecedores, clientes, trabalhadores e entidades legais em diferentes países/regiões.

|Campo                 |descrição      |
|------------------------------|----------------------------|                                                                           
| Nome                | O nome do tipo de registro. |                                                                           
| descrição         | A descrição do tipo de registro. |
| País/região      | O identificador exclusivo do país/região.|
| Autoridade fiscal       | A autoridade fiscal associada ao tipo de registro.|
| Restrito a       | O tipo de restrição que se aplica ao tipo de registro de imposto: Nenhum, pessoa, organização.|
| Formatar              | O formato de validação do tipo de registro de imposto.|
| Pode ser atualizado      | Define se o número de registro para o tipo de registro pode ser atualizado após ser inserido.|
| Exclusivo              | Define se o número do tipo de registro é exclusivo. |
| Principal para o país/região | Se um participante estiver associado a um ou mais endereços em determinado país e a ID de registro for válida para todos esses endereços, você deve designar um endereço como principal para o país. Você só pode registrar um ID como principal. Define se o número de registro pode ser inserido somente para o endereço principal do país. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Atribua um tipo de registro para uma categoria de registro
A categoria de registro é o identificador de registro do país/região aprovado para uso em país/região específico para imposto, alfândega e outros fins. Esta categoria define regras de validação de ID de registro específico (incluindo os dígitos de verificação etc.) e ID de registro de inclusão em diferentes relatórios. Use a página **Administração da organização** &gt; **Catálogo de endereços global** &gt; **Tipos de registro** &gt; **Categorias de registro** para atribuir tipos de registros a um país específico para a categoria de registro suportada.

| Campo            | descrição|
|-----------------------|----------------|
| Tipo de registro     | O tipo de registro em determinado país/região.|
| Restrito a         | O tipo de restrição que se aplica ao tipo de registro de imposto: Nenhum, pessoa, organização.|
| Categoria de registro | O identificador exclusivo do registro aprovado para uso no país. A lista completa de categorias com suporte é mostrada posteriormente neste tópico. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Insira IDs de registro para registros de catálogo de endereços global

O catálogo de endereços global (GAB) contém informações de endereço consolidadas de clientes, fornecedores, contatos, parceiros comerciais e entidades legais. Para obter mais informações, consulte [Visão geral do catálogo de endereços global](../../fin-and-ops/organization-administration/overview-global-address-book.md). Os registros de participantes que são armazenados no catálogo de endereços global podem conter um ou mais registros de endereços. Esses endereços são usados para fins diferentes, como o faturamento ou a entrega. Você pode configurar IDs de registro para informações de endereço para clientes, fornecedores, trabalhadores e entidades legais. Localize o registro do participante (entidade legal, fornecedor, cliente, trabalhador) para o qual você deseja inserir a ID do registro e, clique em **IDs de Registro** nos formulários relacionados à parte, à entidade legal, ao cliente, ao trabalhador para abrir a página **Gerenciar endereços**. Na guia **Registro de imposto**, clique em **Adicionar** e insira as informações a seguir sobre a ID do registro.


|Campo                |descrição                                                |
|---------------------|-----------------------------------------------------------|
| Tipo de registro   | O tipo de registro no país/região selecionado.     |
| Número de inscrição | A ID de registro do participante.                                |
| descrição         | A descrição do número de registro.               |
| Seção             | As informações adicionais sobre o número do registro. |
| Agência emissora      | A autoridade que emitiu o número do registro.        |
| Data da emissão         | A data de emissão do número do registro.              |
| Efetivação           | A data de efetivação do número do registro.           |
| Vencimento          | A data de vencimento do número do registro.          |

> [!NOTE]
> O número de isenção de imposto de entidade legal, fornecedor, cliente pode ser selecionado das IDs de registros relacionados à ID de IVA e inseridos para o participante.

## <a name="search-for-records-by-registration-id"></a>Procure registros por ID de registro
Procure os registros do participante com base em uma ID de registro disponível nos formulários relacionados ao participante, à entidade legal, ao fornecedor, ao cliente e ao trabalhador. Clique em **Pesquisa de ID de registro** para abrir a página **Critérios de pesquisa de ID de registro**. Especifique os critérios de pesquisa e clique em **Localizar**. O sistema exibirá os registros selecionados do catálogo de endereços global e os tipos associados de registro do participante.

## <a name="supported-registration-categories"></a>Categorias de registro suportadas
A tabela a seguir lista os tipos de registro com suporte. Se estiver familiarizado com os campos de IDs de registro do Microsoft Dynamics AX 2012, esta tabela também mapeia esses campos para as categorias de registro do Dynamics 365 Finance.

| Categoria de registro do Finance         |País/Região  | Termo/campo do Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| ID do IVA                                                        | Todos os países da União europeia (EU)|  Número de isenção de imposto (ID de Imposto do tipo legislativo no AX 2012 R3)|
| ID da empresa (COID)                                          | Bélgica República Tcheca Estônia Hungria Letônia Lituânia Polônia Suíça | Número da empresa (EnterpriseNumber) Número de registro (RegNum\_W) Número de registro (RegNum\_W) Número de registro (RegNum\_W) Número de registro (RegNum\_W) Código da empresa (EnterpriseCode) Número de registro (RegNum\_W) UID (UID de tipo legislativo no AX 2012 R3) |
| ID da unidade                                                     | Bélgica            | Número da matriz (BranchNumber)|
| Značka de Spisová (número de registro, agência emissora, seção) | República Tcheca     | Inserir número (CommercialRegisterInsetNumber) Mantido em registro comercial (CommercialRegister) Seção de registro comercial (CommercialRegisterSection)|
| ID de cliente personalizada                                           | Finlândia | Número alfandegário do cliente (CustomsCustomerNumber\_FI)|
| INN                                                           | Federação Russa| INN (INN do tipo legislativo no AX 2012 R3)|
| RRC                                                           | Federação Russa| RRC (RRC do tipo legislativo no AX 2012 R3)|
| OKDP                                                          | Federação Russa| OKDP (OKDP do tipo legislativo no AX 2012 R3)|
| OKPO                                                          | Federação Russa| OKPO (OKPO do tipo legislativo no AX 2012 R3)|
| RCOAD                                                         | Federação Russa| RCOAD (RCOAD do tipo legislativo no AX 2012 R3)|
| OGRN                                                          | Federação Russa| OGRN (OGRN do tipo legislativo no AX 2012 R3) |
| SNILS                                                         | Federação Russa| SNILS (SNILS do tipo legislativo no AX 2012 R3)|
| CIFTS                                                         | Federação Russa| CIFTS (CIFTS do tipo legislativo no AX 2012 R3)|
| Passaporte                                                      | Espanha             | Passaporte|
| Documento de identificação oficial                              | Espanha             | Documento de identificação oficial|
| Certificado de residência                                         | Espanha             | Certificado de residência|
| Outro documento de identificação                                 | Espanha             | Outro documento de identificação|
| Não censurado                                                  | Espanha             | Não disponível no AX 2012 R3|


Para obter mais informações sobre processamento de IDs de registro, incluindo os pré-requisitos obrigatórios, consulte os seguintes registros de tarefas para a ID do IVA no Lifecycle Services (LCS):

-   Configurar a ID do IVA
-   Registro de ID do IVA do fornecedor
-   Pesquisa de participante usando a ID do IVA






[!INCLUDE[footer-include](../../includes/footer-banner.md)]