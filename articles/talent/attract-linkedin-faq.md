---
title: Perguntas frequentes sobre a integração do Attract com o LinkedIn
description: Esse tópico esclarece as dúvidas que você possa ter sobre a integração entre o LinkedIn e o Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: b77ad598ba209dbbd73765c49947e84a3995153d
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550358"
---
# <a name="attract-integration-with-linkedin-faq"></a>Perguntas frequentes sobre a integração do Attract com o LinkedIn

[!include [banner](includes/banner.md)]

O LinkedIn é a maior rede profissional online do mundo. O Microsoft Dynamics Talent: Attract integra-se com o LinkedIn para permitir que você tenha acesso aos melhores talentos do mundo. O Attract permite que você lance trabalhos diretamente no LinkedIn e também permite que você extraia informações do candidato do LinkedIn para o Attract.

## <a name="for-recruiters-and-hiring-managers"></a>Para recrutadores e gerentes de contratação

Veja as respostas a perguntas frequentes sobre como usar o Attract e o LinkedIn juntos.

### <a name="what-linkedin-features-do-i-get-with-attract"></a>Quais recursos do LinkedIn eu obtenho com o Attract?

A integração do Attract com o LinkedIn permite que você execute as seguintes tarefas:

- [Lançar trabalhos no LinkedIn](./attract-post-jobs-to-linkedin.md) (como Listagens Limitadas gratuitas).
- [Exportar informações do candidato do LinkedIn para o Attract](./attract-linkedin-recruiter.md#export-linkedin-candidates-to-attract-with-one-click).
- [Permitir que os candidatos se candidatem aos trabalhos com o LinkedIn](./attract-admin-linkedin.md#set-up-apply-with-linkedin-in-attract).

### <a name="what-do-i-need-before-i-can-post-jobs-to-linkedin"></a>Do que preciso antes que possa lançar trabalhos no LinkedIn?

Seu administrador deve [configurar a integração com o LinkedIn no Attract](./attract-admin-linkedin.md#configure-job-posting-to-linkedin). Depois disso, você estará pronto.

### <a name="how-do-i-post-jobs-to-linkedin-from-attract"></a>Como posso lançar trabalhos no LinkedIn do Attract?

Depois que criar um trabalho no Attract, basta selecionar o botão **Lançar agora** que corresponde ao LinkedIn. Para obter mais informações, consulte [Lançar trabalhos no LinkedIn por meio do Attract](./attract-post-jobs-to-linkedin.md#post-jobs-to-linkedin).

### <a name="can-i-get-candidate-information-from-linkedin-into-attract"></a>Posso obter informações do candidato do LinkedIn no Attract?

Sim. Se vir um bom candidato no LinkedIn, você poderá facilmente exportar as informações desse candidato para o Attract. Para obter mais informações, consulte [Fornecer candidatos com o LinkedIn Recruiter](attract-linkedin-recruiter.md).

### <a name="how-can-i-get-help-accessing-linkedin-from-attract"></a>Como posso obter ajuda para acessa o LinkedIn por meio do Attract?

Caso esteja tendo problemas para entrar ou lançar trabalhos no LinkedIn pelo Attract, consulte [Solucionar problemas de integração com o LinkedIn](./attract-troubleshoot-linkedin.md).

Para outros problemas com o Attract, consulte [Obter suporte para o Talent](./talent-support.md). Para ajuda com o LinkedIn, consulte a [página de suporte do LinkedIn](https://www.linkedin.com/help).

## <a name="for-admins-and-developers"></a>Para administradores e desenvolvedores

Veja as respostas a perguntas frequentes sobre como configurar a integração entre o Attract e o LinkedIn.

### <a name="how-do-i-configure-attract-so-that-recruiters-and-hiring-managers-can-post-jobs-to-linkedin"></a>Como posso configurar o Attract para que os recrutadores e gerentes de contratação possam lançar trabalhos no LinkedIn?

Você pode configure as opções disponíveis na guia **Integração com o LinkedIn** no Centro de administração. Para obter mais informações, consulte [Configurar a integração com o LinkedIn](./attract-admin-linkedin.md).

### <a name="can-i-export-candidate-information-from-linkedin"></a>Posso exportar informações do candidato do LinkedIn?

Sim, mas primeiro você deve configurar a integração com o LinkedIn Recruiter. Para obter mais informações, consulte [Configurar a integração com o LinkedIn](./attract-admin-linkedin.md).

### <a name="how-can-i-post-jobs-to-premium-job-slots-on-linkedin"></a>Como posso lançar trabalhos nos Slots de Trabalho Premium no LinkedIn?

Embora o Attract forneça uma solução poderosa para o lançamento de trabalhos no LinkedIn, é possível que você precise de flexibilidade adicional. Por exemplo, talvez você queira poder lançar nos Slots de Trabalho Premium além das Listagens Limitadas gratuitas, ou talvez você queira que o LinkedIn processe seus lançamentos de trabalho em lote mais de uma vez por dia.

#### <a name="types-of-linkedin-job-posts"></a>Tipos de lançamentos de trabalho do LinkedIn

O LinkedIn oferece os seguintes tipos de lançamentos de trabalho:

- **Listagem limitada** — lançamentos de trabalho gratuitos que são exibidos em resultados de pesquisa quando busca candidatos procuram emprego no LinkedIn e na página de uma empresa no LinkedIn. As Listagens Limitadas são destinadas a candidatos ativos. Este tipo de listagem é o tipo que o Attract fornece ao LinkedIn. Não é possível promover trabalhos da Listagem Limitada no LinkedIn. Se quiser promover Listagens Limitadas, será necessário trabalhar com o LinkedIn para habilitar a Disposição de Trabalho. Para obter mais informações sobre a Disposição de Trabalho, consulte e [Listagens Limitadas versus Slots de Trabalho Premium para Disposição de Trabalho — Perguntas frequentes](https://www.linkedin.com/help/recruiter/answer/79049/limited-listings-vs-premium-job-slots-for-job-wrapping) e [Disposição de Trabalho Plus — Perguntas frequentes](https://www.linkedin.com/help/recruiter/answer/79050/job-wrapping-frequently-asked-questions).
- **Slot de trabalho Premium** — postagens compradas que são exibidas em vários locais no LinkedIn, como o feed do LinkedIn, emails e a área **Trabalhos que podem ser do seu interesse** . Os Slots de Trabalho Premium são destinados a candidatos passivos, mas também são exibidos nas pesquisas de emprego.

O Attract lança trabalhos no LinkedIn como listagens limitadas. Se quiser usar Slots de Trabalho Premium, você deverá usar a Disposição de Trabalho pelo LinkedIn Recruiter. A Disposição de Trabalho exige um contrato de disposição de trabalho com o LinkedIn. Para obter mais informações, consulte [Disposição de Trabalho pelo LinkedIn Recruiter — Visão geral](https://www.linkedin.com/help/recruiter/answer/79037).

#### <a name="frequency-of-batch-processing-on-linkedin"></a>Frequência do processamento em lote no LinkedIn

O LinkedIn processa os lançamentos de trabalho pelo Attract em um lote uma vez por dia. Portanto, pode levar até 48 horas que os trabalhos sejam exibidos no LinkedIn depois de lançados pelo Attract. Se precisar que os trabalhos sejam exibidos no LinkedIn, ou se precisar de flexibilidade adicional, você poderá usar a interface de programação de aplicativos (API) do Recruiter System Connect (API) no LinkedIn. Para obter mais informações, consulte [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect)

#### <a name="table-of-options-for-job-posting-to-linkedin"></a>Tabela de opções para lançamento de trabalhos no LinkedIn

A tabela a seguir descreve as diferentes opções para lançar trabalhos no LinkedIn. Ela Inclui as vantagens de cada opção e informações adicionais.

|  | Attract | Disposição de Trabalho pelo LinkedIn Recruiter | API do Recruiter System Connect |
|---|---|---|---|
| **Descrição** | O Attract lança trabalhos no LinkedIn como um feed XML. | Os contratos da empresa com LinkedIn e ela fornece um feed XML para o lançamento de trabalhos. | O cliente usa a API para sincronizar as informações entre o Attract e o LinkedIn Recruiter. |
| **Que tipo de trabalho posso lançar?** | Listagem Limitada | Slot de trabalho Premium ou Listagem Limitada | Listagem Limitada |
| **Posso promover o trabalho no LinkedIn?** | Não | Slots de Trabalho Premium: sim<br>Listagens Limitadas: não | Não |
| **Com que frequência o LinkedIn lança trabalhos?** | Uma vez por dia | Uma vez por dia | Várias vezes ao dia, conforme definido pela API |
| **Recomendado pelo LinkedIn?** | Não | Sim | Não |
| **Do que preciso?** | Comprar o Attract | Um contrato de disposição de trabalho com o LinkedIn e a compra de Slots de Trabalho Premium | Um contrato de API com o LinkedIn | 
| **Onde eu pode encontrar mais informações?** | [Configurar a integração com o LinkedIn](./attract-admin-linkedin.md) | [Disposição de Trabalho pelo LinkedIn Recruiter — Visão geral](https://www.linkedin.com/help/recruiter/answer/79037) | [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect) |

> [!NOTE]
> Não é necessário uma licença do LinkedIn Recruiter System Connect para lanças trabalhos no LinkedIn com o Attract.

## <a name="see-also"></a>Consulte também

[Configurar a integração com o LinkedIn](./attract-admin-linkedin.md)

[Lançar trabalhos no LinkedIn do Attract](./attract-post-jobs-to-linkedin.md)

[Fornecer candidatos com o LinkedIn Recruiter](./attract-linkedin-recruiter.md)

[Solucionar problemas de integração com o LinkedIn](./attract-troubleshoot-linkedin.md)
