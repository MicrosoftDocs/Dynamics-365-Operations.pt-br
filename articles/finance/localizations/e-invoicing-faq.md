---
title: Perguntas frequentes sobre faturamento eletrônico
description: Este artigo fornece informações relativas a perguntas frequentes sobre faturamento eletrônico.
author: gionoder
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.17
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: cf712c188e27deef4edfce7f5473fec4bb759bdf
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285807"
---
# <a name="electronic-invoicing-faq"></a>Perguntas frequentes sobre Faturamento Eletrônico

[!include [banner](../includes/banner.md)]

Este artigo fornece respostas a perguntas frequentes sobre serviço de faturamento eletrônico. O faturamento eletrônico estende os recursos de faturamento eletrônico que existem no Dynamics 365 Finance, no Dynamics 365 Supply Chain Management e no Dynamics 365 Project Operations. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>O que é importante sobre o faturamento eletrônico e por que deve ser importante para minha organização?

A complexidade operacional e os riscos continuam a se intensificar à medida que as organizações crescem globalmente e aumentam sua presença em todas as regiões. Manter a conformidade e adaptar-se às regulamentações em constante mudança é um desafio crescente e de particular importância quando se trata de faturamento. Tradicionalmente, o faturamento é caro e propenso a erros, uma vez que as empresas dependem de documentos físicos e processos manuais intensos.  

As organizações começaram a deixar de usar faturas físicas para reduzir custos e acelerar o processo de ponta a ponta. As administrações públicas estão recorrendo cada vez mais ao faturamento eletrônico como um dos principais componentes da digitalização dos impostos. Ao exigir que as organizações enviem digitalmente informações de impostos em tempo real para as autoridades fiscais, as administrações públicas podem minimizar a manipulação e a sonegação de impostos e reduzir fraudes. 

O mundo está mudando para o processamentos de documentos sem o uso de papel e se não implementarem o faturamento eletrônico, os clientes correm o risco de ter problemas de conformidade, ter custos desnecessários e ficar atrás da concorrência. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>O Finance, o Supply Chain Management e o Project Operations já incluem a funcionalidade de faturamento eletrônico? Qual o valor que isso agrega a mim, como cliente? 

O faturamento eletrônico estende os recursos de faturamento eletrônico que existem no Finance, no Supply Chain Management e no Project Operations. A funcionalidade também simplifica a adesão aos novos padrões mais recentes de faturamento eletrônico e fornece experiências coerentes para diferentes áreas geográficas no processamento e troca de faturamento eletrônico. Os recursos de faturamento eletrônico liberam uma série de benefícios, incluindo: 

   - Adoção mais fácil e rápida a requisitos específicos do país/região.
   - Padronização de implementações de soluções de faturamento eletrônico. 
   - Rastreabilidade aprimorada do processamento de faturas eletrônicas.  
   - Manutenção mais fácil para a conformidade com os requisitos legais e as práticas comerciais locais em constante mudança. 
   - Pacote de soluções simplificado.
   - Recursos de dimensionamento para um grande volume de documentos enviados que resultam em um retorno mais rápido.
   - Possibilidade de compartilhar suas soluções com outras empresas.

## <a name="does-electronic-invoicing-service-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>O serviço de faturamento eletrônico oferece suporte a instalações locais do Finance, do Supply Chain Management e do Project Operations? 

A plataforma atual não permite o uso da versão local e não há planos para oferecer suporte a ela no futuro.

## <a name="does-electronic-invoicing-service-interface-with-the-vendor-import-automation-feature"></a>A interface do serviço de faturamento eletrônico com o fornecedor importa o recurso de automação?

Não. Há planos para essa interface, mas não há nenhum cronograma planejado. Quando planejado, as datas serão anunciadas nos [Planos de lançamento](/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-service-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>Como o serviço de faturamento eletrônico lida com anexos de arquivos na fatura eletrônica? É necessário um SharePoint Server ao incorporar arquivos PDF no arquivo XML?

Os arquivos anexados à fatura eletrônica são tratados como dados binários incorporados em um elemento XML. Não é necessário um SharePoint Server incorporar arquivos PDF, mas o anexo deve ser armazenado no sistema de gerenciamento de documentos do Finance, do Supply Chain Management e do Project Operations.

## <a name="is-electronic-invoicing-service-available-according-to-the-regulations-of-my-countryregion"></a>O serviço de faturamento eletrônico está disponível de acordo com as regulamentações de meu país/região?

O serviço de faturamento eletrônico é uma plataforma de microsserviços que estará disponível globalmente.

A Microsoft tem planos de publicar formatos de fatura eletrônica e integrações para os países que estão localizados funcionalmente pela Microsoft. Para obter mais informações, consulte [Disponibilidade de recursos de faturamento eletrônico](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Se o formato de faturamento eletrônico para seu país/região não estiver listado, a plataforma pretende oferecer suporte a esse cenário no futuro. Você ainda pode se beneficiar das recursos de configuração que o Faturamento eletrônico tem e configurar o formato de faturamento eletrônico por conta própria ou pode trabalhar com um parceiro/ISV para configurar os formatos para sua organização.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>O Dynamics 365 para Regulatory Services é um novo módulo, como o Human Resources ou o Project Operations, que está vinculado ao Finance ou ao Supply Chain Management? Existem custos adicionais para isso?

O Dynamics 365 para Regulatory Services (RCS) é um serviço de nuvem para a configuração de recursos de globalização. O RCS é gratuito para todos os proprietários de licenças do Finance, do Supply Chain Management e do Project Operations.

Para inscrever-se no RCS, acesse <https://marketing.configure.global.dynamics.com/>.

Para obter mais informações, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing-service-or-just-turn-it-on-in-feature-management"></a>Preciso me inscrever para obter o serviço de faturamento eletrônico ou basta ativá-lo no Gerenciamento de Recursos?

Se você tiver uma licença para o Finance, o Supply Chain Management e o Project Operations, consulte [Introdução à administração de serviço do complemento do Faturamento eletrônico](e-invoicing-get-started-service-administration.md) para se inscrever no Faturamento eletrônico.

## <a name="does-electronic-invoicing-service-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>O serviço de faturamento eletrônico funciona com máquinas virtuais de nível 1? Qual é o ambiente mínimo necessário?

A integração com o serviço de faturamento eletrônico exige pelo menos uma máquina virtual de nível 2 para hospedar o Finance ou o Supply Chain Management. Para obter mais informações sobre o planejamento de ambiente, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-service-have-a-test-mode-for-testing-invoice-submission"></a>O serviço de faturamento eletrônico tem um modo de teste para testar o envio de faturas?

Isso pode ser obtido por meio de configuração. Para testar o envio de faturas, você pode se conectar ao Finance ou ao Supply Chain Management a partir de um ambiente de teste de aceitação do usuário (UAT) e enviar as faturas de teste. O faturamento eletrônico oferece suporte à configuração de certificados digitais de teste e, no caso de faturas eletrônicas que exigem aprovação digital, a configuração de uma URL dos serviços Web de teste publicados pelas autoridades fiscais.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Existe documentação sobre os recursos de faturamento eletrônico prontos para uso específicos do país?

Sim. Para obter informações sobre a disponibilidade de recursos de faturamento eletrônico e os formatos com suporte, consulte [Disponibilidade de recursos de faturamento eletrônico](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

## <a name="does-the-electronic-invoicing-service-allow-a-legal-entity-in-finance-or-supply-chain-management-that-is-configured-for-a-specific-country-to-consume-electronic-invoicing-features-from-different-countryregions"></a>O serviço de faturamento eletrônico permite que uma entidade legal no Finance ou no Supply Chain Management seja configurada para um país específico para consumir recursos de faturamento eletrônico de diferentes países/regiões?

Sim. Os recursos de faturamento eletrônica poderão ser consumidos para processar envios de documentos comerciais independentemente do país da entidade legal, se o seguinte for verdadeiro:

   - O documento comercial que está sendo gerado usa o mapeamento do modelo de documento apropriado.
   - Há uma correspondência entre o documento comercial e as regras de aplicabilidade configuradas no recurso de faturamento eletrônico.

## <a name="does-the-electronic-invoicing-service-use-the-same-configuration-and-design-experience-provided-by-the-electronic-reporting-module-in-finance-and-supply-chain-management"></a>O serviço de faturamento eletrônico usa a mesma experiência de configuração e projeto fornecida pelo módulo de relatório eletrônico no Finance e no Supply Chain Management? 

Sim. As mesmas ferramentas de designer usadas no módulo de relatório eletrônico (ER) no Finance e no Supply Chain Management são usadas para criar e configurar mapeamento de modelos de dados e configurações de formato de arquivo. Essas ferramentas de designer também são usadas em RCS (Regulatory Configuration Services) para criar e configurar mapeamento de modelos de dados e configurações de formato de arquivo usados na configuração dos recursos de faturamento eletrônico.

## <a name="can-the-applicability-rules-be-extended-and-configured-so-that-they-arent-tied-to-any-specific-parameter-such-as-a-legal-entity"></a>As regras de aplicabilidade podem ser estendidas e configuradas de forma que não estejam ligadas a um parâmetro específico, como uma entidade legal?

Sim. As regras de aplicabilidade são totalmente configuráveis. Você pode adicionar ou remover cláusulas, criar operações lógicas e agrupar/desagrupar cláusulas. Para obter mais informações, consulte [Regras de aplicabilidade](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#applicability-rules).

## <a name="does-the-electronic-invoicing-service-support-adding-other-er-format-configurations-to-generate-other-types-of-documents-does-it-support-sending-the-documents-electronically-to-customers-such-as-a-delivery-note"></a>O serviço de faturamento eletrônico dá suporte à adição de outras configurações de formato ER para gerar outros tipos de documentos? Ele dá suporte ao envio de documentos eletronicamente para clientes, como uma nota de entrega?

Você pode usar outras configurações de formato ER para produzir os arquivos de saída desejados. Mas, a configuração do formato ER deve derivar do mesmo mapeamento de modelo de fatura ER configurado no Finance ou no Supply Chain Management para gerar documentos comerciais. O faturamento eletrônico não dá suporte ao envio do arquivo de saída diretamente ao cliente como uma transação EDI pronta para uso.

## <a name="does-the-electronic-invoicing-service-support-exchanging-electronic-invoices-with-customers-does-it-support-configuring-different-invoice-formats-for-the-same-invoice"></a>O serviço de faturamento eletrônico dá suporte à troca de faturas eletrônicas com clientes? Ele oferece suporte à configuração de diferentes formatos de fatura para a mesma fatura?

A capacidade de receber e importar faturas eletrônicas de fornecedores está no roteiro, mas não há suporte ao envio automático de faturas eletrônicas para clientes no momento.

## <a name="does-the-electronic-invoicing-service-extend-to-support-exchanging-edi-messages-with-other-companies"></a>O serviço de faturamento eletrônico se estende para dar suporte à troca de mensagens EDI com outras empresas?

O foco do serviço de faturamento eletrônico é trocar tipos de mensagem de fatura eletrônica orientados pelos requisitos de conformidade regulatória. O recebimento e a importação de faturas eletrônicas de fornecedores está no roteiro, mas o envio de arquivos de fatura eletrônica para os clientes não tem suporte atual, exceto em cenários em que o envio da fatura eletrônica ao cliente é um requisito regulatório.

## <a name="does-the-electronic-invoicing-service-support-importing-or-merging-customizations-made-in-the-er-format-configurations-from-the-legacy-electronic-invoicing-feature"></a>O serviço de faturamento eletrônico oferece suporte para importar ou mesclar personalizações feitas nas configurações de formato ER do recurso de faturamento eletrônico herdado?

Você pode reutilizar as configurações do formato ER no serviço de faturamento eletrônico. Mas, a configuração do formato ER deve derivar do mesmo mapeamento de modelo de fatura ER que o recurso de fatura eletrônica foi desenvolvido para usar e que é configurado no Finance ou no Supply Chain Management para gerar os documentos comerciais.

## <a name="does-the-electronic-invoicing-service-support-issuing-electronic-invoices-from-custom-made-tables-if-so-how-do-you-create-the-er-data-model-configurations-for-these-new-tables-and-entities"></a>O serviço de faturamento eletrônico dá suporte à emissão de faturas eletrônicas a partir de tabelas personalizadas? Em caso afirmativo, como você cria as configurações do modelo de dados ER para essas novas tabelas e entidades?

Sim. Mas, é necessário personalizar o mapeamento de modelo de fatura e adicionar as referências necessárias às tabelas personalizadas ou, dependendo da complexidade, criar um novo mapeamento de modelo de fatura.

## <a name="does-the-electronic-invoicing-service-support-different-web-service-endpoints"></a>O serviço de faturamento eletrônico dá suporte a diferentes pontos de extremidade de serviço Web?

O faturamento eletrônico dá suporte a diferentes pontos de extremidade de serviços Web. Você pode usar a integração configurável com serviços Web REST ou várias integrações parametrizadas de serviço Web específicas de país. Diferentes pontos de extremidade podem ser configurados para os mesmos serviços Web e APIs usando versões diferentes de configurações. Para obter mais informações, consulte [Lista de parâmetros por ação](e-invoicing-setup.md#list-of-parameters-by-action).

## <a name="is-electronic-invoicing-integrated-with-the-various-invoice-operators-apis-from-the-nordic-countries-or-should-that-be-handled-on-a-case-by-case-basis"></a>O faturamento eletrônico está integrado com as várias APIs de operadores de faturas dos países nórdicos ou deve ser tratado caso a caso?

A Microsoft estende continuamente a cobertura funcional para fornecer integrações prontas para uso, usando os recursos de faturamento eletrônico. Para obter mais informações sobre os formatos e as integrações com suporte, consulte a [Disponibilidade de recursos de faturamento eletrônico](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Se você não encontrou a resposta que está procurando, envie um email com sua dúvida para a Equipe de Desenvolvimento de Produtos para <D365EInvoicePreview@microsoft.com>. Vamos contatar você ou melhorar a abrangência dessas perguntas frequentes.
