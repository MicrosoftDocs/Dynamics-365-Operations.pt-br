---
title: Perguntas frequentes sobre faturamento eletrônico
description: Este tópico fornece informações relativas a perguntas frequentes sobre faturamento eletrônico.
author: gionoder
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1ba1a6c5542c10306d4b7494d33e7ff04504fa95
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893769"
---
# <a name="electronic-invoicing-faq"></a>Perguntas frequentes sobre faturamento eletrônico

[!include [banner](../includes/banner.md)]

Este tópico fornece respostas a perguntas frequentes sobre faturamento eletrônico. O faturamento eletrônico estende os recursos de faturamento eletrônico que existem no Dynamics 365 Finance, no Dynamics 365 Supply Chain Management e no Dynamics 365 Project Operations. 

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

## <a name="does-electronic-invoicing-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>O Faturamento eletrônico oferece suporte a instalações locais do Finance, do Supply Chain Management e do Project Operations? 

A plataforma atual não permite o uso da versão local e não há planos para oferecer suporte a ela no futuro.

## <a name="does-electronic-invoicing-interface-with-the-vendor-import-automation-feature"></a>A interface do Faturamento eletrônico com o fornecedor importa o recurso de automação?

Não. Há planos para essa interface, mas não há nenhum cronograma planejado. Quando planejado, as datas serão anunciadas nos [Planos de lançamento](/dynamics365/release-plans/).

## <a name="how-does-electronic-invoicing-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>Como o Faturamento eletrônico lida com anexos de arquivos na fatura eletrônica? É necessário um SharePoint Server ao incorporar arquivos PDF no arquivo XML?

Os arquivos anexados à fatura eletrônica são tratados como dados binários incorporados em um elemento XML. Não é necessário um SharePoint Server incorporar arquivos PDF, mas o anexo deve ser armazenado no sistema de gerenciamento de documentos do Finance, do Supply Chain Management e do Project Operations.

## <a name="is-electronic-invoicing-available-according-to-the-regulations-of-my-countryregion"></a>O Faturamento eletrônico está disponível de acordo com as regulamentações de meu país/região?

O Faturamento eletrônico é uma plataforma de microsserviços que está disponível globalmente.

A Microsoft tem planos de publicar formatos de fatura eletrônica e integrações para os países que estão localizados funcionalmente pela Microsoft. Para obter mais informações, consulte [Disponibilidade de recursos de faturamento eletrônico](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

Se o formato de faturamento eletrônico para seu país/região não estiver listado, a plataforma pretende oferecer suporte a esse cenário no futuro. Você ainda pode se beneficiar das recursos de configuração que o Faturamento eletrônico tem e configurar o formato de faturamento eletrônico por conta própria ou pode trabalhar com um parceiro/ISV para configurar os formatos para sua organização.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>O Dynamics 365 para Regulatory Services é um novo módulo, como o Human Resources ou o Project Operations, que está vinculado ao Finance ou ao Supply Chain Management? Existem custos adicionais para isso?

O Dynamics 365 para Regulatory Services (RCS) é um serviço de nuvem para a configuração de recursos de globalização. O RCS é gratuito para todos os proprietários de licenças do Finance, do Supply Chain Management e do Project Operations.

Para inscrever-se no RCS, acesse <https://marketing.configure.global.dynamics.com/>.

Para obter mais informações, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md).

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing--or-just-turn-it-on-in-feature-management"></a>Preciso me inscrever para obter o Faturamento eletrônico ou basta ativá-lo no Gerenciamento de Recursos?

Se você tiver uma licença para o Finance, o Supply Chain Management e o Project Operations, consulte [Introdução à administração de serviço do complemento do Faturamento eletrônico](e-invoicing-get-started-service-administration.md) para se inscrever no Faturamento eletrônico.

## <a name="does-electronic-invoicing-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>O Faturamento eletrônico funciona com máquinas virtuais de nível 1? Qual é o ambiente mínimo necessário?

A integração com o Faturamento eletrônico requer pelo menos uma máquina virtual de nível 2 para hospedar o Finance ou o Supply Chain Management. Para obter mais informações sobre o planejamento de ambiente, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-have-a-test-mode-for-testing-invoice-submission"></a>O Faturamento eletrônico tem um modo de teste para testar o envio de faturas?

Isso pode ser obtido por meio de configuração. Para testar o envio de faturas, você pode se conectar ao Finance ou ao Supply Chain Management a partir de um ambiente de teste de aceitação do usuário (UAT) e enviar as faturas de teste. O faturamento eletrônico oferece suporte à configuração de certificados digitais de teste e, no caso de faturas eletrônicas que exigem aprovação digital, a configuração de uma URL dos serviços Web de teste publicados pelas autoridades fiscais.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Existe alguma documentação sobre os recursos de faturamento eletrônico prontos para uso que são específicos do país?

Sim. Para obter informações sobre a disponibilidade de recursos de faturamento eletrônico e os formatos aos quais eles oferecem suporte, consulte [Disponibilidade de recursos de faturamento eletrônico](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Se você não encontrou a resposta que está procurando, envie um email com sua dúvida para a Equipe de Desenvolvimento de Produtos para <D365EInvoicePreview@microsoft.com>. Vamos contatar você ou melhorar a abrangência dessas perguntas frequentes.