---
title: ​Perguntas frequentes sobre ativação​
description: Este tópico lista as perguntas frequentes sobre como ativar um projeto de implementação do Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64a85840be328702a06779390fe383fd1896fd04
ms.sourcegitcommit: d66fd72342931fad25a696b251c05781280d36c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "4011402"
---
# <a name="go-live-faq"></a>​Perguntas frequentes sobre ativação​ 

Este tópico lista as perguntas frequentes sobre como ativar um projeto de implementação do Dynamics 365 Human Resources. 

## <a name="when-can-i-configure-and-request-my-production-environment"></a>Quando posso configurar e solicitar meu ambiente de produção? 

Normalmente, um ambiente de produção é implantado depois de atender aos seguintes critérios:

- Todas as personalizações têm conclusão de código.
- O teste de aceitação do usuário (UAT) está concluído.
- O cliente saiu da solução.
- Não há problemas de bloqueio para a ativação. 

Quando clientes qualificados estão nesse estágio, a equipe do Microsoft FastTrack trabalhará com a equipe do projeto para realizar uma avaliação de ativação. 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a>Quais são os pré-requisitos para a implantação de um ambiente de produção? 

Para obter uma lista dos pré-requisitos, consulte  [Preparar-se para a ativação](hr-admin-go-live-prepare.md). 

## <a name="what-is-a-go-live-assessment"></a>O que é uma avaliação de ativação?  

A avaliação de ativação é parte do  [programa Microsoft FastTrack ](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview). Durante esta revisão, o arquiteto de soluções avalia se um projeto de implementação está pronto para uma transição e uma ativação bem-sucedida. Esta revisão é obrigatória para todos os projetos de implementação antes que você possa solicitar a ativação em um ambiente de produção. 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a>Nossos ambientes de Área restrita são implantados no data center EUA Central. Queremos que nossos Ambientes de produção sejam implantados no datacenter Oeste dos EUA. Posso selecionar Oeste dos EUA como o data center em minha configuração de Produção? 

O LCS não impede que você selecione um data center diferente ao implantar um ambiente do Human Resources, mas é altamente recomendável não selecionar um data center diferente.  

Se você deseja que seu ambiente de Produção esteja no data center Oeste dos EUA, primeiro implante os ambientes de Área Restrita no data center Oeste dos EUA, teste-os e saia. 

Para obter informações sobre como selecionar o datacenter correto, consulte [Requisitos de rede](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements). 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a>Que nível de acesso tenho para os recursos do Azure para meus ambientes do Human Resources?  

O acesso aos ambientes do Human Resources é limitado. Não é possível acessar a máquina virtual (VM) ou o Serviços de Informações da Internet da Microsoft (IIS). Também não é possível acessar o banco de dados por meio do Microsoft SQL Server Management Studio. 

Embora não seja possível acessar diretamente os recursos do Azure ou o ambiente do Dynamics 365 Human Resources diretamente, há recursos adicionais que você pode usar para acessar seus dados:

- Você pode implantar um banco de dados SQL do Azure no seu próprio locatário do Azure e usar o recurso BYOD (Trazer Seu Próprio Banco de Dados) para sincronizar dados. Para obter mais informações, consulte [Trazer seu próprio banco de dados (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).

- Você pode usar a integração do Common Data Service para sincronizar as entidades selecionadas no banco de dados do Common Data Service. Para obter mais informações, consulte [Entidades do Common Data Service](hr-developer-entities.md). 

## <a name="how-often-is-my-production-database-backed-up"></a>Com que frequência é feito o backup do meu banco de dados de produção? 

Os bancos de dados são protegidos por backups automáticos nas seguintes frequências:

| Tipo de backup | Frequência |
| --- | --- |
| Backup completo do banco de dados | Semanalmente |
| Backup diferencial do banco de dados | A cada 12-24 horas |
| Backup do log de transações | A cada 5 a 10 minutos |

A Microsoft mantém backups suficientes para permitir a Recuperação Pontual (PITR) nos últimos sete dias. 

Para obter mais informações sobre os backups, consulte  [Saber mais sobre backups automáticos do Banco de Dados SQL](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database). 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a>Posso solicitar uma cópia do backup do meu banco de dados de produção? 

Nº No entanto, você pode enviar uma solicitação de serviço de atualização de banco de dados para copiar seu Ambiente de produção para o Ambiente de área restrita. Você pode implantar um banco de dados SQL do Azure no seu próprio locatário do Azure e usar o recurso BYOD (Trazer Seu Próprio Banco de Dados) para sincronizar dados do seu Ambiente de produção. Para obter mais informações, consulte [Trazer seu próprio banco de dados (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database). 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a>Como posso mover meu ambiente de Área restrita para Produção para ativação? 

Como um recurso de cópia não está disponível para mover seu ambiente de uma Área restrita para um Ambiente de produção, você deverá usar pacotes de dados para mover os dados para o Ambiente de produção.  

É recomendável manter uma lista clara das entidades configuradas em sua Área restrita ao longo do projeto. Em seguida, teste o processo de substituição e migração de quaisquer pacotes de dados necessários para sua ativação. Você deve mover manualmente todos os pacotes de dados para o Ambiente de produção quando estiver pronto para a ativação. 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a>O que devo fazer se meu Ambiente de produção estiver inativo? 

Para relatar uma interrupção de Produção, siga o processo descrito em  [Informar uma interrupção de produção](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage). 

 ## <a name="see-also"></a>Consulte também

 [Preparar para a ativação](hr-admin-go-live-prepare.md)