---
title: Migração para a Otimização de Planejamento para o planejamento mestre
description: Este tópico fornece informações sobre o novo mecanismo de planejamento mestre, a Otimização de Planejamento, e a migração do mecanismo existente.
author: ChristianRytt
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: crytt
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: e9aa911ca22ca2beeffe6bec95f17f94142065e4
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348748"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>Migração para a Otimização de Planejamento para o planejamento mestre

[!include [banner](../includes/banner.md)]

O mecanismo de planejamento mestre interno está programado para se tornar obsoleto (preterido). Ele está sendo substituído pelo Suplemento Otimização de Planejamento para Microsoft Dynamics 365 Supply Chain Management. Este tópico fornece informações sobre o impacto em implantações novas e existentes. Ele inclui informações sobre as ações necessárias.

A Otimização de Planejamento permite que os cálculos do planejamento mestre ocorram fora do Supply Chain Management e de seu banco de dados SQL do Azure. Os benefícios associados à Otimização de Planejamento incluem desempenho aprimorado e impacto minimizado no banco de dados SQL durante as execuções do planejamento mestre. Como execuções de planejamento rápido podem ser feitas mesmo durante o horário de expediente, os planejadores podem reagir imediatamente à demanda ou às alterações de parâmetro.

Para obter mais informações sobre a Otimização de Planejamento, consulte [Visão geral da Otimização de Planejamento](planning-optimization/planning-optimization-overview.md).

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>Obsolescência do mecanismo de planejamento mestre existente

A Microsoft está no processo de tornar o mecanismo de planejamento interno obsoleto em favor da Otimização de Planejamento. Essa alteração afeta todos os ambientes de nuvem. As instalações locais não são afetadas. Na versão 10.0.16 e posteriores, você receberá uma mensagem de erro se executar o planejamento mestre interno sem gerar ordens de produção planejadas. No entanto, a execução do planejamento mestre será concluída com êxito apesar da mensagem de erro.

Para obter mais informações sobre a obsolescência do mecanismo de planejamento interno, consulte os comunicados em [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md).

## <a name="migration-messages-and-exceptions"></a>Migração, mensagens e exceções

Os proprietários de ambientes existentes que executam o mecanismo de planejamento mestre interno sem gerar ordens de produção planejadas receberão um email com detalhes sobre o processo de exceção. Recomendamos que você trabalhe com um parceiro para avaliar e planejar a migração para a Otimização de Planejamento.

Como foi mencionado, você receberá uma mensagem de erro na versão 10.0.16 e posteriores se executar o planejamento mestre interno sem gerar ordens de produção planejadas. Essa mensagem de erro inclui orientações sobre migração e instruções para solicitação de uma exceção.

### <a name="new-deployments"></a>Implantações novas

A Otimização de Planejamento deve ser considerada o mecanismo de planejamento mestre padrão para todas as novas implantações na nuvem. Em geral, a Otimização de Planejamento deve ser usada para todas as novas implantações que não geram ordens de produção planejadas durante o planejamento mestre. Se uma nova implantação depender de funcionalidades às quais a Otimização de Planejamento não oferece suporte no momento, você poderá solicitar uma exceção para continuar a usar o mecanismo de planejamento mestre interno.

### <a name="existing-deployments"></a>Implantações existentes

Os proprietários de implantações existentes baseadas na nuvem que dependem do planejamento mestre devem planejar a migração para a Otimização de Planejamento. Se a sua implementação depender de funcionalidades às quais a Otimização de Planejamento não oferece suporte no momento, você poderá solicitar uma exceção para continuar a usar o mecanismo de planejamento mestre interno.

Para ambientes que atualmente usam processos do planejamento mestre que estão se tornando obsoletos, a Microsoft enviará um email ao administrador do ambiente. Esse email fornecerá informações sobre as ações necessárias para a migração ou a solicitação de uma exceção.

## <a name="the-exception-process"></a>O processo de exceção

Você pode solicitar uma exceção se precisar continuar a usar o mecanismo de planejamento mestre interno, pois seus processos empresariais dependem muito de, pelo menos, um recurso que não está implementado na Otimização de Planejamento no momento. Para obter uma lista de recursos disponíveis, consulte [Análise de ajuste da Otimização de Planejamento](planning-optimization/planning-optimization-fit-analysis.md).

No momento, as exceções da migração para a Otimização de Planejamento só são relevantes se o seu processo de planejamento mestre não incluir a produção (ou seja, ordens de produção planejadas geradas pelo planejamento mestre) e se você precisar do mecanismo de planejamento mestre interno além da versão 10.0.15.

Depois que os recursos necessários forem disponibilizados, a Microsoft fornecerá um período de carência até a expiração da exceção. O administrador do ambiente será informado quando os recursos necessários estiverem disponíveis e o período de carência tiver começado.

O fluxograma abaixo resume as informações fornecidas neste tópico para que você possa decidir rapidamente se deve solicitar uma exceção. Se precisar solicitar uma exceção, preencha e envie a [Questionário de exceção e migração do plano de otimização](https://go.microsoft.com/fwlink/?linkid=2144962).

![Fluxograma de exceção.](media/exception-diagram.png "Fluxograma de exceção")

> [!NOTE]
> Você só pode solicitar uma exceção para locatários que incluem, ou incluirão, um ambiente de produção, não apenas para locatários com ambientes de área restrita. Se você precisar desabilitar o erro de exceção da Otimização de Planejamento em um ambiente de área restrita IaaS (infraestrutura como serviço), execute a consulta SQL fornecida em [Ambientes de área restrita](#faq-sandbox).

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>​Ambientes de área restrita​

Posso usar o planejamento mestre interno no meu ambiente de área restrita? Preciso de uma exceção?

**Resposta:** Normalmente, as exceções não são relevantes para ambientes de área restrita porque o erro de exceção da Otimização de Planejamento não impede que o mecanismo de planejamento mestre interno seja executado com êxito. No entanto, se a mensagem de erro incomoda você, é possível desabilitá-la em um ambiente de área restrita IaaS (não Service Fabric) executando a seguinte consulta no seu banco de dados:

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a>Ambientes locais

Meu ambiente é local. Preciso de uma exceção?

**Resposta:** Não. Uma exceção não é necessária para ambientes locais. Você pode continuar a usar o planejamento mestre interno. O administrador do ambiente será informado se qualquer ação for necessária.

### <a name="production-scenarios"></a>Cenários de produção

Usamos ordens de produção planejadas, mas estou preocupado com o que acontecerá quando atualizarmos para a versão 10.0.16. Devo executar alguma ação?

**Resposta:** Você não deve se preocupar. Você pode continuar a usar o planejamento mestre interno na versão 10.0.16. No entanto, recomendamos que você avalie se a migração para a Otimização de Planejamento pode começar com a funcionalidade atual. Também recomendamos que você se mantenha informado sobre novas funcionalidades.

### <a name="email-from-microsoft"></a>Email da Microsoft

Nosso administrador de ambiente recebeu um email da Microsoft. Esse email informa que devemos migrar para a Otimização de Planejamento ou solicitar uma exceção. Preciso executar alguma ação?

**Resposta:** Sim. Seu ambiente será afetado a menos que você siga as instruções do email. Você pode migrar para a Otimização de Planejamento até a data especificada ou solicitar uma exceção usando o link no email. Esse link abre um questionário. Depois de concluir e enviar o questionário, você receberá uma resposta por email. Embora esse processo seja manual, a Microsoft tenta responder dentro de uma semana após o envio do questionário.

### <a name="error-messages"></a>Mensagens de erro

Estou usando a versão 10.0.16 ou posteriores e recebi a seguinte mensagem de erro ao executar o planejamento mestre. O planejamento mestre está bloqueado?

> Você recebeu essa mensagem de erro porque o mecanismo de planejamento mestre interno foi usado para cenários com suporte da Otimização de Planejamento. Você deve migrar para a Otimização de Planejamento agora, pois o planejamento mestre interno atual será preterido. Observe que essa execução do planejamento mestre foi concluída com êxito.
>
> Caso sua migração tenha fortes dependências de recursos pendentes, uma exceção para continuar o uso do mecanismo de planejamento mestre interno poderá ser solicitada.
>
> Preencha o seguinte questionário para começar e, se for o caso, solicitar uma exceção da migração para a Otimização de Planejamento.

**Resposta:** Não, o planejamento mestre não está bloqueado. A execução do planejamento mestre foi concluída com êxito e você pode usar o resultado como de costume. No entanto, para evitar o recebimento dessa mensagem de erro durante futuras execuções do planejamento mestre, você deve migrar para a Otimização de Planejamento imediatamente ou solicitar uma exceção usando o link na mensagem de erro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
