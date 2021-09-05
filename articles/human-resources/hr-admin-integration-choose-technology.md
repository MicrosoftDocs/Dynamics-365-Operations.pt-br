---
title: Escolher uma tecnologia de integração de dados
description: Este tópico fornece informações sobre a integração com dados gerenciados por Human Resources.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d58a42236b07bf177e09aee50a207ffdf2ed1435
ms.sourcegitcommit: 72a82e9aeabbdecf57e1aee72975c63eba75143a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7414705"
---
# <a name="choose-a-data-integration-technology"></a>Escolher uma tecnologia de integração de dados

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico fornece informações sobre a integração com dados gerenciados pelo Dynamics 365 Human Resources. Ele descreve diferentes tecnologias de integração para ajudá-lo a decidir quais tecnologias atendem melhor às suas necessidades.

## <a name="data-integration-background"></a>Plano de fundo da integração de dados

Dados comerciais como é um ativo importante que torna a sua empresa exclusiva. Os dados de sua empresa são altamente valiosos. Você pode usar os relacionamentos entre os dados obtidos em toda a sua empresa para melhorar os processos comerciais e a Business Intelligence na organização. Nos esforçamos para fornecer acesso fácil, seguro e estável a dados de sua empresa, independentemente do sistema de origem.

Historicamente, a integração de dados entre vários sistemas tem sido difícil. A Microsoft está tomando medidas para facilitar a integração de dados, e um grande passo para o alcance dessa meta é dado por meio do [Dataverse](/powerapps/maker/common-data-service/data-platform-intro).

O Human Resources está tornando o Dataverse a interface pública preferida para seus dados. Com o tempo, esperamos que todos os dados mais importantes gerenciados pelo Human Resources sejam expostos no Dataverse. Recomendamos o Dataverse como a tecnologia de preferência para a maioria dos aplicativos de integração.

Percebemos que Dataverse ainda não é consegue conter todos os dados exigidos por seu aplicativo. Também sabemos que a linha de tempo de seu projeto pode exigir uma tecnologia alternativa. Lembre-se de que nós sabemos quando o Dataverse não atende às suas necessidades de integração.

## <a name="integration-technologies"></a>Tecnologias de integração

As seções a seguir descrevem as diferentes tecnologias de integração de dados disponíveis para uso com o Human Resources.

### <a name="dataverse-tables"></a>Tabelas do Dataverse

O Dataverse é a interface de dados pública preferida para o Human Resources. Ele cresceu da plataforma Dynamics 365 XRM que é usada pelas soluções do [Dynamics 365 Customer Engagement](/dynamics365/?panel=customer-engagement#pivot=business-apps).

O Dataverse fornece uma plataforma e API para tabelas de dados. Quando você implanta Human Resources, ele se conecta a uma instância do Dataverse. As entidades para os dados de Human Resources são implantadas nessa instância do Dataverse. As tabelas e seus dados estão disponíveis para aplicativos que possam se conectar à instância do Dataverse. O Human Resources sincroniza dados de e para tabelas do Dataverse.

> [!NOTE]
> Entidades do Human Resources correspondem a tabelas do Dataverse. Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

Quando as tabelas de dados exigidas pelos aplicativos de integração estiverem no Dataverse, você poderá usar o [Dataverse e as APIs com suporte](/powerapps/?panel=developer#pivot=home). Entre as APIs permitidas está a [API Web do Dynamics 365](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), que fornece uma implementação OData para acesso aos dados do Dataverse.

As tabelas do Dataverse e as APIs associadas são a melhor opção para acessar dados do Human Resources de aplicativos Web, serviços Web/APIs e de qualquer outro aplicativo que se conecte a feeds do OData.

> [!NOTE]
> Com a decisão de tornar o Dataverse a interface de dados preferida para o Human Resources sendo relativamente recente, talvez você descubra que as entidades de dados do Human Resources de que precisa para sua integração ainda não estejam disponíveis no Dataverse.
> </br>
> Para obter uma lista de entidades do Human Resources disponíveis no Dataverse, consulte [Human Resources e Dataverse](/dynamics365/unified-operations/talent/corehrentities).
> </br>
> Se as entidades do Human Resources exigidas para sua integração ainda não estiverem disponíveis, você precisará aguardar que as entidades de dados sejam disponibilizadas ou precisará usar uma de outras tecnologias de integração descritas abaixo.
> </br>
> Por padrão, a integração do Dataverse está desativada em ambientes novos que não incluem os dados de demonstração fornecidos. Ela está ativada em novos ambientes que incluem os dados de demonstração, e os ambientes começam a sincronizar dados quando eles são provisionados. Depois que o ambiente estiver pronto para sincronizar dados, você poderá ativar a integração.

### <a name="dmfdixf-entities"></a>Entidades DMF/DIXF

Human Resources, criados principalmente na mesma plataforma que os aplicativos Finance and Operations, fornecem um [Estrutura de gerenciamento de dados (DMF)](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json). A DMF também é conhecida como estrutura de exportação de importação de dados (DIXF). Os Human Resources fornecem um conjunto de entidades de dados que você pode usar para importar e exportar dados de recursos humanos. Embora as tabelas do Dataverse sejam a interface de integração de dados preferida para o Human Resources, as entidades DMF ainda são úteis em algumas circunstâncias, como:

- As tabelas do Dataverse ainda não estão disponíveis.

- A integração requer recursos de importação/exportação de dados em massa de alto desempenho.

> [!NOTE]
> Entidades do Human Resources correspondem a tabelas do Dataverse. Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

As entidades DMF no momento fornecem a cobertura de dados mais completa para dados do Human Resources.

A DMF não é adequada para integrações em tempo real, por exemplo, quando você precisa de comentários imediatos do usuário em uma interface de usuário. As operações de pacote são trabalhos em lote programados e geralmente têm um mínimo de uma latência de 1-2 minutos antes que o serviço de lote obtenha o trabalho para execução, além de qualquer hora necessária para concluir a operação de importação/exportação.

A DMF pode ser a melhor opção quando há necessidade de alta produtividade (por exemplo, uma importação/exportação de muitos milhares de registros programada para ocorrer à noite).

> [!NOTE]
> A DMF não está disponível para o Attract e Onboard.

### <a name="dmf-package-rest-api"></a>API REST do pacote DMF

A DMF fornece uma [API REST](/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) para manipular pacotes de dados. Essa API pode ser usada para interagir programaticamente com a DMF, permitindo ações como:

- Importar um pacote de dados.

- Exportar um pacote de dados.

- Verificar o status de uma operação de importação/exportação.

A API REST do Pacote DMF tem suporte total no Human Resources.

### <a name="azure-sql-db-byod"></a>Banco de Dados SQL do Azure (BYOD)

A DMF também fornece um recurso avançado (conhecido como [Traga seu Próprio Banco de Dados](/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database) ou BYOD) que permite ao Human Resources exportar dados para seu próprio banco de dados SQL do Microsoft Azure. Esse recurso oferece excelente flexibilidade. Quando os dados estão presentes no seu próprio banco de dado SQL, você pode fazer uso de qualquer aplicativo ou middleware que possa se conectar a um armazenamento de dados SQL.

O BYOD é principalmente uma solução somente leitura. Embora você possa manipular e armazenar qualquer dado que desejar no banco de dados SQL do Azure (por exemplo, para mashups de dados), os dados armazenados no banco do dados SQL do Azure não serão sincronizados novamente com o Human Resources..

A abordagem BYOD é apropriada soluções de relatório, integrações de dados, mashups de dados e como uma fonte de dados para um pipeline do [Azure Data Factory](/azure/data-factory/).

> [!NOTE]
> A BYOD não está disponível para o Attract e Onboard.

### <a name="odata-enabled-entities"></a>Entidades habilitadas para OData

A maioria das entidades DMF também é habilitada para acesso por meio do serviço de dados (OData) do Human Resources. A documentação fornecida para o [serviço Finance and Operations OData](/dynamics365/unified-operations/dev-itpro/data-entities/odata) se aplica a recursos humanos, exceto para criar suas próprias entidades expostas por OData.

Embora o Dataverse e a implementação do OData fornecida pelo Dataverse (por meio da [API Web do Dynamics 365](/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) sejam preferíveis ao serviço de dados do Human Resources, este último atualmente tem uma cobertura de entidade mais completa para os dados do Human Resources.

### <a name="excel-add-in"></a>Suplemento do Excel

O [Suplemento do Excel](/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json) faz uso de entidades habilitadas para OData sob a superfície. É um modo conveniente de um usuário final recuperar e modificar os dados do Human Resources pro meio da interface de usuário conhecida do Excel.

O Suplemento do Excel é adequado para importações/exportações de dados ad hoc por especialistas em domínio comercial. Para uma integração de dados recorrente que requer automação programática, outra tecnologia de integração será mais apropriada.

### <a name="data-integrator"></a>Integrador de Dados

Você pode usar o [serviço Integrador de dados](/powerapps/administrator/data-integrator) para integrar dados para e do Dataverse. O Integrador de Dados permite que você defina projetos de integração (geralmente com base em modelos predefinidos que os desenvolvedores de aplicativos ajustaram para integrações específicas). Você pode agendar projetos de integração para execução automática em um plano recorrente ou para execução manual.

Os projetos de integradores de dados são apropriados para integrações de lote do Dataverse. Elas são uma ótima opção para integrações entre a família de aplicativos do Dynamics 365. Por exemplo, a Microsoft fornece um modelo do Integrador de Dados para integrar dados do Human Resources ao Dynamics 365 Finance. Você pode obter mais informações sobre o modelo em [Integração de Dynamics 365 Human Resources para Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

O Integrador de Dados aceita o [Power Query](/power-query/power-query-what-is-power-query) por meio de seu [recurso de Consulta Avançada](/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering). O Power Query oferece filtragem e transformação de dados eficientes e flexíveis, incluindo o idioma de fórmula M avançado. O Power Query deverá ser familiar se você tiver desenvolvido relatórios do Power BI.

## <a name="deciding-on-an-integration-technology"></a>Decidindo sobre uma tecnologia de integração

Com tantas tecnologias de integração diferentes disponíveis, a decisão sobre qual abordagem de integração usar, às vezes, pode ser desgastante. À medida que a cobertura de dados no Dataverse for evoluindo, a decisão se tornará mais fácil, e o Dataverse será a interface de dados preferida na maioria dos casos. Mas, até lá, você pode achar que o Dataverse ainda não atende às suas necessidades. A tabela a seguir resume algumas das principais características das opções de tecnologia de integração.

| Tecnologia/ferramenta/API    | Integrações recorrentes                   | Síncrono/assíncrono                    | Acesso programático por meio de uma API        | Volumes de dados apropriados                                   | Cobertura de dados                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Tabelas do Dataverse           | Sim, usando o Integrador de Dados ou middleware | Sinc. Assíncrona, Lote (por meio do Integrador de Dados) | Sim, por meio da API Web do Dynamics 365 (OData) | Varia com o caso de uso (oferece suporte à paginação para uso interativo) | Aprimorando<sup>2</sup>                       |
| Entidades DMF           | Sim, agendada por meio de middleware        | Assíncrono, Lote                                | Sim, por meio da API REST do Pacote DMF         | Alto (centenas de milhares de registros)                    | Alta                                |
| API REST do Pacote DMF   | Sim, agendada por meio de middleware        | Assíncrono, Lote                                | Sim                                       | Alto (centenas de milhares de registros)                    | API aceita todas as entidades DMF       |
| BYOD                   | Sim, agendada pelo Admin do Human Resources        | Assíncrono, Lote                                | Não<sup>3</sup>                                    | Alto (centenas de milhares de registros)                    | Aceita todas as entidades DMF           |
| Entidades habilitadas para OData | Sim, usando middleware                    | Sincronizar                                        | Sim, por meio do Serviço de Dados (OData) do Human Resources  | Varia com o caso de uso (oferece suporte à paginação para uso interativo) | Alta                                |
| Suplemento do Excel           | Não                                       | Sincronizar                                        | Não                                        | Médio (dezenas de milhares de registros)                      | Aceita todas as entidades habilitadas para OData |
| Integrador de Dados        | Sim, agendada no Integrador de Dados        | Assíncrono, Lote                                | Não                                        | Varia com o caso de uso                                       | Oferece suporte a todas as tabelas do Dataverse           |

<sup>2</sup>A Microsoft está investindo fortemente na crescente cobertura de dados para tabelas do Dataverse. Recomendamos o uso de Dataverse quando a cobertura estiver disponível. No momento, a cobertura de dados do Dataverse é baixa com relação às entidades habilitadas para OData e DMF.

<sup>3</sup>O banco de dados SQL pode ser acessado de modo programático.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
