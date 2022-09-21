---
title: Novidades e alterações no Dynamics 365 Commerce 10.0.29 (outubro de 2022)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Commerce 10.0.29.
author: josaw1
ms.date: 08/17/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 6e457864f51159f46f45e9b8969863c9d34c5786
ms.sourcegitcommit: 56677afde87a9176f879482a7af223e251801d5d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "9475894"
---
# <a name="whats-new-or-changed-in-dynamics-365-commerce-10029-october-2022"></a>Novidades ou alterações no Dynamics 365 Commerce 10.0.29 (outubro de 2022)

[!include [banner](../includes/banner.md)]


Este artigo lista os recursos novos ou alterados na versão 10.0.29 do Microsoft Dynamics 365 Commerce. Esta versão tem um número de compilação 10.0.1326 e está disponível na seguinte agenda:

- **Versão preliminar de teste:** agosto de 2022
- **Disponibilidade geral da versão (atualização automática):** setembro de 2022
- **Disponibilidade geral da versão (atualização automática):** outubro de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este artigo para incluir recursos que foram adicionados à compilação após a publicação inicial deste artigo.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---------|------------------|----------------|--------------| 
| B2B | [Habilitar suporte ao contrato de venda em todos canais](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-b2b-sales-agreement-contract-based-pricing) | Este recurso permite que as organizações de vendedor B2B (entre empresas) usem contratos de venda no Commerce Headquarters para definir preços com base em contratos para seus compradores. Quando um comprador B2B compra no site de comércio eletrônico, o preço com base no contrato configurado para a organização de compradores B2B é automaticamente aplicado a toda a descoberta de produtos, compra e experiência de finalização de compra. | Gerenciamento de recursos<p>*Suporte ao contrato de venda em todos canais comerciais* |
| Customer Service | [Habilitar Customer Service com Omnicanal para Customer Service do Dynamics 365](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/chat-dynamics-365-commerce-omnichannel-customer-service) | Uma experiência de atendimento ao cliente de primeira classe é fundamental para fornecer uma experiência de comércio personalizada e incrível para consumidores. Existem vários pontos de contato comerciais no momento, como lojas físicas, canais online e canais sociais. Os consumidores esperam uma experiência de suporte personalizada em todos esses pontos de contato. Esse recurso ajuda a aumentar as conversões de carrinhos para vendas, aumentar o contato personalizado com os consumidores e aprimorar o serviço de atendimento ao consumidor por meio da integração ao Omnicanal para Customer Service do Dynamics 365. | Habilitado por administradores/responsáveis |
| Comércio eletrônico | Suporte para comparação de produtos no comércio eletrônico | Permite que os compradores comparem os produtos em uma ampla gama de categorias, de forma que possam tomar a decisão de compra correta. Este recurso está disponível para os sites business-to-consumer (B2C) e B2B. | Construtor de sites | 
| Cartões-presente | Suporte para tabelas de cartão-presente de varejo para compartilhamento de dados entre empresas | Matrizes dinâmicas oferecem suporte à capacidade de habilitar o compartilhamento de dados entre empresas para tabelas específicas na arquitetura do Dynamics. Neste recurso, o Dynamics 365 Commerce adiciona suporte para compartilhamento de dados entre empresas para tabelas de cartão-presente de varejo. Portanto, um cartão-presente em uma empresa pode agora ter seus dados duplicados para outra empresa no ambiente. As alterações feitas na tabela de cartão-presente da empresa de origem serão compartilhadas na tabela de cartão-presente da empresa duplicada. | Desenvolvedores |
| Globalização | [Habilitar recursos de localização do Commerce para o novo SDK do Commerce](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-commerce-localization-features-new-commerce-sdk) | O novo recurso oferece a possibilidade de habilitar os recursos de localização do Commerce no Commerce headquarters usando a estrutura ou os parâmetros de gerenciamento de recursos. As amostras de integração fiscal agora estão incluídas no novo SDK do Commerce e dão suporte a pacotes independentes. Esse recurso também permite a adoção do aplicativo Store Commerce por clientes globais do Commerce.<p><p>Esta versão inclui os recursos de localização do Commerce e as amostras de integração fiscal para a [Áustria](../localizations/emea-aut-fi-sample.md), [República Tcheca](../localizations/emea-cze-fi-sample.md), [França](../localizations/emea-fra-cash-registers.md), [Alemanha](../localizations/emea-deu-fi-sample.md), [Itália](../localizations/emea-ita-fpi-sample.md), [Noruega](../localizations/emea-nor-cash-registers.md) e [Polônia](../localizations/emea-pol-fpi-sample.md). | Habilitado por administradores/responsáveis |
| Desempenho | Remover dependência RTS para cenários "editar cliente" | Alta disponibilidade e alto desempenho são as expectativas padrão para os canais de ponto de venda (PDV) e comércio eletrônico. Para ajudar a cumprir essas expectativas, os canais do Dynamics 365 Commerce não precisam mais depender da comunicação em tempo real com o Commerce Headquarters quando as informações do cliente são editadas. A capacidade de editar as informações do cliente de forma assíncrona para clientes assíncronos e não assíncronos pode ajudar a reduzir as chamadas em tempo real para o Commerce Headquarters. | Habilitado por administradores/responsáveis |

## <a name="feature-state-changes-in-this-release"></a>Alterações do estado do recurso nesta versão

A tabela a seguir lista os recursos que se tornaram obrigatórios ou ativados por padrão na versão 10.0.29. Todos esses recursos serão automaticamente ativados para o seu sistema assim que você atualizar para a versão 10.0.29. Não é possível desativar os recursos obrigatórios, mas os recursos ativados por padrão ainda podem ser desativados usando o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

A tabela também lista recursos que anteriormente estavam na versão preliminar pública, mas que foram alterados para se tornarem disponíveis na versão 10.0.29. Essa alteração indica que agora os recursos são recomendados para uso em ambientes de produção. Esses recursos são desativados por padrão, salvo indicação em contrário. Portanto, você deve usar o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativá-los, caso queira usá-los.

| Recurso | Cargo | Novo estado do recurso |
| --- | --- | --- |
| BrazilRetailLocalizationFeature_BR |(Brasil) Funcionalidade do Commerce específica para o Brasil | Ativado por padrão |
| RetailAdvancedGTETaxAdjustmentFeature | (Índia) Aplicar GST calculada para transações de varejo no Retail POS para demonstrativos de varejo | Ativado por padrão |
| RetailChronologicalInvoicePostingFeature_IT | (Itália) Habilitar faturas de varejo lançadas sem ordem cronológica | Ativado por padrão |
| RetailDiscountWithoutTaxAdjustingFeature_MX | (México) Ajuste de desconto no Retail CFDI Global | Ativado por padrão |
| RetailFiscalIntegrationConfigurationEnhancementFeature | Substituições do perfil técnico de integração fiscal | Ativado por padrão |
| RetailFiscalIntegrationConnectorLocationFeature | Integração fiscal direta de terminais de PDV | Ativado por padrão |
| RetailFiscalIntegrationLocalStorageBackupEnableFeature | Backup de armazenamento local de integração fiscal | Ativado por padrão |
| RetailFiscalIntegrationPostponeFiscalRegistrationFeature | Registro adiado de documentos | Ativado por padrão |
| RetailFiscalIntegrationRegistrationProcessTerminalExceptionFeature | Estado do Registro Fiscal de Terminais de PDV | Ativado por padrão |
| RetailGSTInvoiceAddressTaxCalculationFeature_IN | (Índia) Calcular GST com base no endereço da fatura para ordens de comércio eletrônico | Ativado por padrão |
| RetailInvoicesDefaultSalesDocumentStatusFeature_PL | (Polônia) Status padrão do documento de venda para faturas de varejo | Ativado por padrão |
| RetailRecalculateRoundingOfTaxBaseAmountsFeature_MX | (México) Recálculo de arredondamento para valores base de impostos no recurso global do CFDIs do Retail. | Ativado por padrão |
| RetailSupplementaryInvoiceFeature | Habilitar faturas suplementares para transações de cash and carry concluídas em lojas de varejo | Ativado por padrão |
| RetailInventoryBufferAndInventoryLevelEnableFeature   |  Habilitar buffers de estoque e níveis de estoque    |  Ativado por padrão|
|RetailInboundOutboundInventoryValidationFeature|   Habilitar validação na operação de estoque de entrada e saída do PDV   |   Ativado por padrão   |
|  RetailInventoryChannelCalculationConsolidationFeature    |  Lógica de cálculo de estoque no canal de comércio eletrônico aprimorada |   Ativado por padrão   |
|RetailInventoryAdjustmentsInPointOfSaleFeature|    Ajustes de estoque no ponto de venda   |  Ativado por padrão  |
| RetailMultiplePickupDeliveryModeFeature |  Suporte para vários modos de entrega de retirada     |   Obrigatório    |
|  RetailProductAvailabilityOptimizationFeature |   Cálculo de disponibilidade de produto otimizado  |  Obrigatório |
|   RetailPricingDataManagerV2Feature   |   Melhorar o desempenho do mecanismo de preço do Commerce |   Obrigatório |
|  RetailPricingPreventUnintendedRecalculationFeature   | Impedir cálculo de preço não intencional para ordens de comércio    |  Obrigatório  |
| RetailTeamsIntegration    |   Habilitar integração com o Microsoft Teams| Obrigatório   |  
| ConsumerEFDSyncProcessFeature_BR | (Brasil) NFC-e processamento síncrono | Ativado por padrão |
| RetailFiscalIntegrationInternalAndExternalServicesEnableFeature | Suporte a conectores internos e externos na estrutura de integração fiscal | Obrigatório |
| RetailTaxRegistrationIdEnableFeature_BR | (Brasil) Pesquisar clientes no Retail POS por números de inscrição de impostos | Obrigatório |
| RetailTaxRegistrationIdEnableFeature_IN | (Índia) Pesquisar clientes no Retail POS por números de inscrição de impostos | Obrigatório |
| RetailTaxRegistrationIdEnableFeature_IT | (Itália) Gerenciamento de informações de clientes no Retail POS | Obrigatório |
| RetailTaxRegistrationIdEnableFeature_PL | (Polônia) Gerenciamento de informações de clientes no Retail POS | Obrigatório |
| RetailUpdateReturnOriginalTransactionIdGlobalEnableFeature_IN | (GST de varejo da Índia) Atualizar notas de crédito com referências a faturas originais | Obrigatório |
| RetailUserDefinedCertificateProfileFeature | Perfis de certificado definidos pelo usuário para lojas de varejo | Obrigatório |
  

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Commerce 10.0.29 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.29 dos aplicativos de Finanças e Operações (outubro de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md). 

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte da versão 10.0.29, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559&dbType=3&qc=ec3e3846199f5d3a27a0c4949e3902ffdbc87560f0cf928c4838b3bdd421633c). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 e nuvens do setor: plano 2 do ciclo de lançamentos de 2022

Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira [Dynamics 365 e nuvens do setor: plano 2 do ciclo de lançamentos de 2022](/dynamics365-release-plan/2022wave2/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-features"></a>Recursos removidos e preteridos

Os [recursos removidos ou preteridos no artigo Dynamics 365 Commerce](removed-deprecated-features-commerce.md) descrevem os recursos que foram removidos ou preteridos para o Commerce.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no artigo [Recursos removidos ou preteridos no Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 meses antes da remoção.

Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
