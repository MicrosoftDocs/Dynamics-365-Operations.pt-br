---
title: Requisitos de dimensionamento de hardware para ambientes locais
description: Este artigo lista os requisitos de dimensionamento de hardware para um ambiente local.
author: sericks007
ms.date: 06/02/2021
ms.topic: article
ms.prod: dynamics-365
ms.service: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: chwolf
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 88b677eab6a691003e26356acf7bb8de666bb55d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890019"
---
# <a name="hardware-sizing-requirements-for-on-premises-environments"></a>Requisitos de dimensionamento de hardware para ambientes locais

[!include [banner](../includes/banner.md)]

Antes de iniciar o processo de dimensionamento do hardware e da infraestrutura para um ambiente local, familiarize-se com os [Requisitos do sistema para implantações em nuvem](system-requirements.md) e as [Instruções de configuração e de implantação](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md) para obter um sólido conhecimento da infraestrutura subjacente.

> [!NOTE]
> Preste muita atenção nas práticas recomendadas de configuração do sistema para obter o desempenho ideal.

Depois de examinar a documentação, inicie o processo de estimativa do seu volume de usuários simultâneos e transacional e o dimensionamento do seu ambiente com base na taxa média de transferência principal.

## <a name="factors-that-affect-sizing"></a>Fatores que afetam o dimensionamento

Todos os fatores mostrados na ilustração a seguir contribuem para o dimensionamento. Quanto mais detalhadas forem as informações coletadas, mais preciso será o dimensionamento. O dimensionamento do hardware, sem os dados de suporte, provavelmente será impreciso. O requisito mínimo absoluto para os dados necessários é a carga de pico de linhas de transação por hora.

[![Dimensionamento de hardware para ambientes locais.](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)

Exibido da esquerda para a direita, o primeiro e mais importante fator necessário para estimar com precisão o dimensionamento é um perfil de transações ou uma caracterização de transações. É importante sempre localizar o volume transacional de pico por hora. Se houver vários períodos de pico, então esses períodos precisarão ser definidos com exatidão.

Além de compreender a carga que afeta a sua infraestrutura, também é necessário compreender mais detalhes sobre estes fatores:

- **Transações** – geralmente, as transações têm determinados picos durante o dia/semana. Isso depende principalmente do tipo de transação. Normalmente, as entradas de horas e de despesas mostram picos uma vez por semana, enquanto as entradas de Ordem de venda com frequência vêm em massa por meio de integração ou As entradas de horas e de despesa geralmente picos mostram uma vez por semana, enquanto as entradas da ordem de venda que vêm em massa na integração ou pouco a pouco durante o dia.
- **Número de usuários simultâneos** – o número de usuários simultâneos é o segundo fator de dimensionamento mais importante. Você não consegue obter estimativas confiáveis de dimensionamento com base no número de usuários simultâneos e, portanto, se esses forem os únicos dados disponíveis, estime um número aproximado e então revisite esse item quando tiver mais dados. Uma definição exata de usuários simultâneos significa que:

    - Os usuários nomeados não são usuários simultâneos.
    - Os usuários simultâneos são sempre um subconjunto de usuários nomeados. 
    - A carga de trabalho de pico de fine a simultaneidade máxima para o dimensionamento.

    Os critérios para usuários simultâneos são que o usuário atenda a todos estes critérios:

    - Conectado.
    - Transações/consultas de trabalho no momento da contagem.
    - Não é uma sessão ociosa.

- **Composição de dados** – principalmente ligado a como o seu sistema será instalado e configurado. Por exemplo, quantas entidades legais,você terá, quantos itens, quantos níveis de BOM e qual será a complexidade da sua configuração de segurança. Cada um desses fatores terá um pequeno impacto no desempenho e, portanto, podem ser compensados usando opções inteligentes quando se trata de infraestrutura.
- **Extensões** – as personalizações podem ser simples ou complexas. O número de personalizações e a natureza e o uso de complexidade têm um impacto variado no tamanho da infraestrutura necessária. Para personalizações complexas, é recomendável conduzir avaliações de desempenho para garantir que elas não sejam testadas apenas para obtenção de eficiência, mas também para ajudar a compreender as necessidades da infraestrutura. Isso é ainda mais crítico quando as extensões não estão codificadas de acordo com as práticas recomendadas de desempenho e escalabilidade.
- **Relatórios e análise** – esses fatores geralmente incluem a execução de consultas pesadas em vários bancos de dados no sistema. Compreender e reduzir a frequência de execução de relatórios caros ajudará você a compreender o impacto deles.
- **Soluções de terceiros** – essas soluções, como os ISVs, têm as mesmas implicações e recomendações das extensões.

## <a name="sizing-your-environment"></a>Dimensionamento de seu ambiente

Para compreender seus requisitos de dimensionamento, você precisará saber o volume de pico de transações que precisam ser processadas. A maioria dos sistemas auxiliares, como o Management Reporter ou o SSRS, é menos crítica. Como resultado, este documento se concentra principalmente no AOS e no SQL Server.

> [!NOTE]
> Em geral, as camadas de computação se expandem e devem ser configuradas de um modo N+1. Isso significa que, se você estimar três AOS, adicione um quarto AOS. A camada de banco de dados deve ser definida em uma configuração AlwaysOn altamente disponível.

## <a name="sql-server-oltp"></a>SQL Server (OLTP)

### <a name="sizing"></a>Dimensionamento

- Três mil a quinze mil linhas de transação por hora, por núcleo, no servidor de banco de dados.
- Taxa fundamental do AOS para SQL típica de 3:1 para o SQL Server principal. Os núcleos adicionais serão necessários com base na configuração de alta disponibilidade escolhida.

    - As operações de processamento pesado no banco de dados podem retroceder isso para 2:1.

- Os fatores a seguir influenciam as variações:

    - Configurações de parâmetro em uso.
    - Níveis de extensões.
    - Uso de funcionalidade adicional, como log e alertas de banco de dados. O registro de logs de banco de dados extremo reduzirá ainda mais a taxa de transferência por hora, por núcleo, para abaixo das três mil linhas.
    - Complexidade de composição de dados – um plano de contas simples versus um plano de contas refinado detalhado tem implicações na taxa de transferência (como um exemplo).
    - Caracterização de transações.
    - De 2 GB a 16 GB de memória para cada núcleo.
    - Bancos de dados auxiliares no servidor de banco de dados, como os bancos de dados do Management reporter e do SSRS.
    - Temp DB = 15% do tamanho do banco de dados, com a quantidade de arquivos igual ao de processadores físicos.
    - Tamanho e taxa de transferência de SAN com base no volume/uso total de transações simultâneas.

### <a name="high-availability"></a>Alta disponibilidade

Recomenda-se sempre usar um SQL Server em uma configuração de cluster ou de espelhamento. O segundo nó SQL deve ter o mesmo número de núcleos do que o nó principal.

### <a name="active-directory-federation-services-ad-fs"></a>Serviços de Federação do Active Directory (AD FS)

Para o dimensionamento do AD FS, consulte a [documentação da Capacidade do Servidor AD FS](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity).

A [planilha de dimensionamento](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx) está disponível para o planejamento do número de instâncias em sua implantação.

## <a name="aos-online-and-batch"></a>AOS (Online e lote)

### <a name="sizing"></a>Dimensionamento

- Dimensionamento por volume/uso de transações

    - 2 mil a 6 mil linhas por núcleo
    - 16 GB por instância
    - Caixa padrão – 4 a 24 núcleos
    - 10 a 15 usuários Enterprise por núcleo
    - 15 a 25 usuários de Atividade por núcleo
    - 25 a 50 Membros de equipe por núcleo

- Lote

    - 1 a 4 threads de lote por núcleo
    - Tamanho baseado na caracterização de janela de lote

- Observe que o AOS, o Gerenciamento de Dados e o Lote estão na mesma função no Service Fabric. É necessário dimensionar para estas três cargas de trabalho combinadas e você não precisa separá-las como no Microsoft Dynamics AX 2012.
- Aplicam-se aqui os mesmos fatores de variação para o SQL Server

### <a name="high-availability"></a>Alta disponibilidade

- Verifique se você tem pelo menos um a dois outros AOS disponíveis a mais do que a estimativa.
- Verifique se você tem pelo menos três a quatro hosts virtuais disponíveis.

## <a name="management-reporter"></a>Management reporter

Na maioria dos casos, a menos que sejam usados extensivamente, os requisitos mínimos recomendados com dois nós devem funcionar bem. Você só precisará de mais de dois nós somente nos casos onde houver um uso pesado. Dimensione como necessário.

## <a name="sql-server-reporting-services"></a>SQL Server Reporting Services

Para a versão de disponibilidade geral, somente um nó do SSRS poderá ser implantado. Monitorar seu nó do SSRS ao testar e aumente o número de núcleos disponíveis para o SSRS em caso de necessidade. Verifique se você tem um nó pré-configurado secundário disponível em um host virtual que seja diferente da VM do SSRS. Isso será importante se houver um problema com a máquina virtual que hospeda o SSRS ou o host virtual. Se esse for o caso, será necessário substituí-los.

A partir da versão 10.0.17, é possível configurar os nós do SSRS adicionais para atingir alta disponibilidade. Para obter mais informações, consulte [Configurar a alta disponibilidade para os nós do SQL Server Reporting Services (SSRS)](../../dev-itpro/deployment/onprem-ssrsha.md).

## <a name="environment-orchestrator"></a>Orchestrator no ambiente

O serviço Orchestrator é o serviço que gerencia sua implantação e a comunicação relacionada com o LCS. Esse serviço é implantado como o serviço principal do Service Fabric e exige pelo menos três VMs. Esse serviço está localizado no mesmo lugar dos serviços de orquestração do Service Fabric. Isso deve ser ajustado à carga de pico do cluster. Para obter mais informações, consulte [Planejar e preparar sua implantação de cluster autônomo do Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="virtualization-and-oversubscription"></a>Virtualização e excesso de subscrição

Os serviços de missão crítica como o AOS devem ser hospedados em Hosts virtuais com recursos dedicados - núcleos, memória e disco.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
