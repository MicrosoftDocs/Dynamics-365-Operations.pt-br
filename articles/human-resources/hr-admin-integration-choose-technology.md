---
title: Escolher uma tecnologia de integração de dados
description: Este artigo fornece orientação sobre várias opções para integração a dados gerenciados pelo Human Resources, descrevendo as características de diferentes tecnologias de integração para que os integradores possam tomar decisões acertadas relacionadas às tecnologias que melhor atendem às suas necessidades.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f2de5dd41c00e6546b4a4feadaf5774430d572bb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029879"
---
# <a name="choose-a-data-integration-technology"></a>Escolher uma tecnologia de integração de dados

O Dynamics 365 Human Resources gerencia dados comerciais que são úteis em vários processos de negócios. Este artigo fornece orientação sobre várias opções para integração a dados gerenciados pelo Human Resources, descrevendo as características de diferentes tecnologias de integração para que os integradores possam tomar decisões acertadas relacionadas às tecnologias que melhor atendem às suas necessidades.

## <a name="data-integration-vision"></a>Visão da integração de dados

A Microsoft vê os dados comerciais como um ativo importante que torna a sua empresa exclusiva. Os dados de sua empresa são altamente valiosos. Os dados coletados e mantidos por uma parte da empresa relacionam-se aos dados reunidos por outra parte da empresa, e essas relações podem ser usadas para melhorar os processos de negócios e o business intelligence na organização. Fornecer acesso fácil, seguro e estável a seus dados comerciais, independentemente do sistema que "possui" os dados é um princípio fundamental da visão que temos da integração de dados ao Human Resources.

Historicamente, a integração de dados entre vários sistemas tem sido difícil.
A Microsoft está tomando medidas para facilitar a integração de dados, e um grande passo para o alcance dessa meta é dado por meio do [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Daqui para frente, o Human Resources está tornando o Common Data Service a interface pública preferida para seus dados. Com o tempo, esperamos que todos os dados mais importantes gerenciados pelo Human Resources sejam expostos no Common Data Service. Recomendamos o Common Data Service como a tecnologia de preferência para a maioria dos aplicativos de integração. Embora tenhamos consciência de que nem todos os dados que seu aplicativo pode exigir estejam presentes no momento no Common Data Service, e que as linhas do tempo do seu projeto podem exigir uma tecnologia alternativa, avise-nos quando o Common Data Service não atender às suas necessidades de integração.

## <a name="integration-technologies"></a>Tecnologias de integração

As seções a seguir descrevem as diferentes tecnologias de integração de dados disponíveis para uso com o Human Resources.

### <a name="common-data-service-entities"></a>Entidades do Common Data Service

O Common Data Service é a interface de dados pública preferida para o Human Resources. O Common Data Service foi criado com base em uma plataforma sólida, tendo crescido fora da plataforma Dynamics 365 "XRM", sobre a qual as soluções [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement) foram criadas.

O Common Data Service fornece uma plataforma para entidades de dados e uma API para acessar essas entidades. Quando o Human Resources é implantado na sua organização, ele é conectado a uma instância do Common Data Service e as entidades que mantêm os dados do Human Resources são implantadas dentro dessa instância do Common Data Service, disponibilizando as entidades e seus dados para qualquer aplicativo que possa se conectar com a instância do Common Data Service. Dependendo dos aplicativos de recursos humanos que você está usando, o Human Resources realiza operações de dados diretamente nas entidades do Common Data Service (esse é o caso do Attract e Onboard) ou sincroniza os dados bidirecionalmente nas entidades do Common Data Service.

Depois que as entidades de dados que expõem os dados exigidos pelos seus aplicativos estiverem presentes no Common Data Service, você poderá fazer pleno uso do [Common Data Service e das APIs que ele permite](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). Entre as APIs permitidas está a [API Web do Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), que fornece uma implementação OData para acesso aos dados do Common Data Service.

As entidades do Common Data Service e as APIs associadas são a melhor opção para acessar os dados do Human Resources de aplicativos Web, serviços/APIs Web e de qualquer outro aplicativo que se conecte aos feeds do OData.

> [!NOTE]
> Com a decisão de tornar o Common Data Service a interface de dados preferida para o Human Resources sendo relativamente recente, talvez você descubra que as entidades de dados do Human Resources de que precisa para sua integração ainda não estejam disponíveis no Common Data Service<sup>1</sup>. Se as entidades do Human Resources exigidas para sua integração ainda não estiverem disponíveis, você precisará aguardar que as entidades de dados sejam disponibilizadas ou precisará usar uma de outras tecnologias de integração descritas abaixo.
> 
> Por padrão, a integração do Common Data Service está desativada em ambientes novos que não incluem os dados de demonstração fornecidos. Ela está ativada em novos ambientes que incluem os dados de demonstração, e os ambientes começam a sincronizar dados quando eles são provisionados. Depois que o ambiente estiver pronto para sincronizar dados, você poderá ativar a integração.

<sup>1</sup>Para obter uma lista de entidades do Human Resources disponíveis no Common Data Service, consulte [Human Resources e Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities). Quanto ao Attract e Onboard, todas as entidades estão disponíveis no Common Data Service.

### <a name="dmfdixf-entities"></a>Entidades DMF/DIXF

O Human Resources, criado basicamente na mesma plataforma que os aplicativos do Finance and Operations, fornece uma [DMF (Estrutura de Gerenciamento de Dados)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json), às vezes também conhecida como Estrutura de Importação/Exportação de Dados ou DIXF, e um conjunto de entidades de dados que podem ser usados para importar/exportar dados bidirecionalmente no Human Resources. Embora as entidades do Common Data Service sejam a interface de integração de dados preferida para o Human Resources, as entidades DMF ainda serão úteis em algumas circunstâncias, como:

- As entidades do Common Data Service ainda não estão disponíveis.

- A integração requer recursos de importação/exportação de dados em massa de alto desempenho.

As entidades DMF atualmente fornecem a cobertura de dados mais completa para dados do Human Resources.

A DMF não é adequada para integrações em tempo real (por exemplo, quando é necessário um comentário imediato do usuário em uma interface de usuário), pois as operações de pacote são trabalhos em lotes programados e geralmente têm uma latência mínima de 1 a 2 minutos antes que o serviço em lote execute o trabalho, além de exigir a conclusão da operação de importação/exportação a qualquer hora.

A DMF pode ser a melhor opção quando há necessidade de alta produtividade (por exemplo, uma importação/exportação de muitos milhares de registros programada para ocorrer à noite).

> [!NOTE]
> A DMF não está disponível para o Attract e Onboard.

### <a name="dmf-package-rest-api"></a>API REST do pacote DMF

A DMF fornece uma [API REST](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) para manipular pacotes de dados. Essa API pode ser usada para interagir programaticamente com a DMF, permitindo ações como:

- Importar um pacote de dados.

- Exportar um pacote de dados.

- Verificar o status de uma operação de importação/exportação.

A API REST do Pacote DMF tem suporte total no Human Resources: Core HR.

### <a name="azure-sql-db-byod"></a>Banco de Dados SQL do Azure (BYOD)

A DMF também fornece um recurso avançado (geralmente conhecido como [Traga seu Próprio Banco de Dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database) ou BYOD) que permite ao Human Resources exportar dados para seu próprio banco de dados SQL do Microsoft Azure. Isso proporciona uma enorme flexibilidade, pois quando os dados estão presentes no seu próprio banco de dado SQL, você pode fazer uso de qualquer aplicativo ou middleware que possa se conectar a um armazenamento de dados SQL.

A abordagem BYOD geralmente deve ser considerada uma solução somente leitura. Embora você possa manipular e armazenar qualquer dado que desejar no banco de dados SQL do Azure (por exemplo, para mashups de dados), os dados armazenados no banco do dados SQL do Azure não serão sincronizados novamente com o Human Resources..

A abordagem BYOD é apropriada soluções de relatório, integrações de dados, mashups de dados e como uma fonte de dados para um pipeline do [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/).

> [!NOTE]
> A BYOD não está disponível para o Attract e Onboard.

### <a name="odata-enabled-entities"></a>Entidades habilitadas para OData

A maioria das entidades DMF também é habilitada para acesso por meio do serviço de dados (OData) do Human Resources. A documentação fornecida para o [serviço OData do Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) geralmente também se aplica ao Human Resources, embora a documentação sobre como criar suas próprias entidades expostas pelo OData não se aplique.

Embora o Common Data Service e a implementação do OData fornecida pelo Common Data Service (por meio da [API Web do Dynamics 365](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))) sejam preferíveis ao serviço de dados do Human Resources, este último atualmente tem uma cobertura de entidade mais completa para os dados do Human Resources.

### <a name="excel-add-in"></a>Suplemento do Excel

O [Suplemento do Excel](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) faz uso de entidades habilitadas para OData sob a superfície. É um modo conveniente de um usuário final recuperar e modificar os dados do Human Resources pro meio da interface de usuário conhecida do Excel.

O Suplemento do Excel é adequado para importações/exportações de dados ad hoc por especialistas em domínio comercial. Para uma integração de dados recorrente que requer automação programática, outra tecnologia de integração será mais apropriada.

### <a name="data-integrator"></a>Integrador de Dados

A experiência do administrador do Common Data Service fornece um [serviço de Integrador de Dados](https://docs.microsoft.com/powerapps/administrator/data-integrator) que pode ser usado para integração de dados ao Common Data Service. O Integrador de Dados pode ser usado para definir projetos de integração (geralmente com base em modelos predefinidos que os desenvolvedores de aplicativos ajustaram para integrações específicas). Os projetos de integração podem ser agendados para execução automática em um plano recorrente ou para execução manual.

Os projetos do Integrador de Dados são adequados para integrações em lote do Common Data Service e uma excelente escolha para integrações entre a família de aplicativos do Dynamics 365. Como exemplo, a Microsoft fornece um modelo pronto para uso do Integrador de Dados que pode ser usado para integrar dados do Human Resources ao Dynamics 365 Finance. Para obter mais informações, consulte [Integração do Dynamics 365 Human Resources ao Dynamics 365 Finance](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

O Integrador de Dados também aceita o [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) (por meio de seu [recurso de Consulta Avançada](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering)).
O Power Query oferece filtragem e transformação de dados eficientes e flexíveis, incluindo a linguagem de fórmula M avançada, que, provavelmente, será familiar àqueles que têm experiência no desenvolvimento de relatórios do Power BI.

## <a name="deciding-on-an-integration-technology"></a>Decidindo sobre uma tecnologia de integração

Com tantas tecnologias de integração diferentes disponíveis, a decisão sobre qual abordagem de integração usar, às vezes, pode ser desgastante. Com o tempo, e especialmente à medida que a cobertura de dados no Common Data Service for evoluindo, a decisão se tornará mais fácil, e o Common Data Service será a interface de dados preferida na maioria dos casos. Mas, até lá, você pode achar que o Common Data Service ainda não atende às suas necessidades. A tabela a seguir ajuda a resumir algumas das principais características das diversas opções de tecnologia de integração.

| Tecnologia/ferramenta/API    | Integrações recorrentes                   | Síncrono/assíncrono                    | Acesso programático por meio de uma API        | Volumes de dados apropriados                                   | Cobertura de dados                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Entidades do Common Data Service           | Sim, usando o Integrador de Dados ou middleware | Sinc. Assíncrona, Lote (por meio do Integrador de Dados) | Sim, por meio da API Web do Dynamics 365 (OData) | Varia com o caso de uso (oferece suporte à paginação para uso interativo) | Aprimorando<sup>2</sup>                       |
| Entidades DMF           | Sim, agendada por meio de middleware        | Assíncrono, Lote                                | Sim, por meio da API REST do Pacote DMF         | Alto (centenas de milhares de registros)                    | Alta                                |
| API REST do Pacote DMF   | Sim, agendada por meio de middleware        | Assíncrono, Lote                                | Sim                                       | Alto (centenas de milhares de registros)                    | API aceita todas as entidades DMF       |
| BYOD                   | Sim, agendada pelo Admin do Human Resources        | Assíncrono, Lote                                | Não<sup>3</sup>                                    | Alto (centenas de milhares de registros)                    | Aceita todas as entidades DMF           |
| Entidades habilitadas para OData | Sim, usando middleware                    | Sincronizar                                        | Sim, por meio do Serviço de Dados (OData) do Human Resources  | Varia com o caso de uso (oferece suporte à paginação para uso interativo) | Alta                                |
| Suplemento do Excel           | Não                                       | Sincronizar                                        | Não                                        | Médio (dezenas de milhares de registros)                      | Aceita todas as entidades habilitadas para OData |
| Integrador de Dados        | Sim, agendada no Integrador de Dados        | Assíncrono, Lote                                | Não                                        | Varia com o caso de uso                                       | Aceita todas as entidades do Common Data Service           |

<sup>2</sup>A Microsoft está investindo pesadamente no aumento da cobertura de dados para entidades do Common Data Service e recomenda o Common Data Service como a interface de dados preferida quando a cobertura estiver disponível. No momento, a cobertura de dados do Common Data Service é baixa com relação às entidades habilitadas para OData e DMF.

<sup>3</sup>O banco de dados SQL pode ser acessado de modo programático.

## <a name="summary"></a>Resumo

Os dados comerciais são um ativo valioso, mas seu valor pode ser bastante reduzido se for difícil usar os dados para suas finalidades específicas (como relatórios, mashups de dados ou aplicativos personalizados). O Dynamics 365 Human Resources fornece várias tecnologias para trabalhar com dados fora da interface do usuário do aplicativo Human Resources, permitindo que os aplicativos de integração acessem os dados. Este tópico descreveu as tecnologias de integração disponíveis e algumas de suas características principais. Essas informações podem ajudar você a tomar melhores decisões sobre quais abordagens usar para seus projetos de integração.

