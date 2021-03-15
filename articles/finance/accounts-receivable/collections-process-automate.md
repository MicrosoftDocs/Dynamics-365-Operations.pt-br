---
title: Automação do processo de cobranças
description: Este tópico descreve a configuração de estratégias do processo de cobranças que identificam automaticamente as faturas de cliente que exigem um lembrete por email, uma atividade de cobrança (como um telefonema) ou uma carta de cobrança a ser enviada ao cliente.
author: panolte
manager: AnnBe
ms.date: 08/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: a63058904df72a7fda5a67ed1e6a846eed393ce0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969692"
---
# <a name="collections-process-automation"></a>Automação do processo de cobranças

[!include [banner](../includes/banner.md)]

Este tópico descreve a configuração de estratégias do processo de cobranças que identificam automaticamente as faturas de cliente que exigem um lembrete por email, uma atividade de cobrança (como um telefonema) ou uma carta de cobrança a ser enviada ao cliente. 

As organizações gastam uma quantidade significativa de tempo pesquisando relatórios de saldo antigos, contas de clientes e faturas em aberto para determinar quais clientes precisam ser contatados sobre uma fatura em aberto ou um saldo de conta. Essa pesquisa tira tempo do agente de cobrança que seria gasto na comunicação com os clientes para cobrar saldos vencidos ou resolver contestações de faturas. A automação do processo de cobranças permite configurar uma abordagem baseada em estratégias para o processo de cobrança. Isso ajuda a aplicar as atividades de cobrança consistentemente, fornecendo lembretes por email personalizados ou processo programado para enviar cartas de cobrança. 

## <a name="collections-process-setup"></a>Configuração do processo de cobranças
Você pode usar a página **Configuração do processo de cobranças** (**Crédito e cobranças > Configuração > Configuração do processo de cobranças**) para criar um processo de cobranças automatizado que vai agendar atividades, enviar mensagens de email e criar e lançar cartas de cobrança de clientes. As etapas do processo são baseadas na fatura em aberto principal ou mais antiga. Cada etapa usa essa fatura para determinar qual comunicação ou atividade deve ocorrer com um cliente específico.  

### <a name="process-hierarchy"></a>Hierarquia de processos
Cada grupo de clientes só pode ser atribuído a uma hierarquia de processos. A classificação hierárquica dessa etapa identifica qual processo terá precedência se um cliente for incluído em mais de um grupo com uma hierarquia de processos atribuída. A ID do grupo determina quais clientes serão atribuídos ao processo. 

Os dias silenciosos são usados para garantir que um cliente não seja contatado com muita frequência pelo processo automatizado.  Por exemplo, se os dias silenciosos forem definidos como dois, um cliente não será contatado pelo processo automatizado por pelo menos dois dias, mesmo se a fatura principal original tiver sido integralmente liquidada. 

Para excluir clientes da automação de processos se o saldo da conta ou o saldo da fatura for menor que um valor definido, defina o campo **Excluir do processo** como **Sim** e insira o valor.

## <a name="process-details"></a>Detalhes do processo
**Descrição** é usada para identificar a finalidade ou o nome da etapa na hierarquia.

**Tipo de ação** define se a etapa vai criar uma atividade, enviar um email ou criar uma carta de cobrança.

**Documento comercial** define o modelo usado para criar o tipo de ação.  Pode ser um modelo de atividade, um modelo de email ou uma carta de cobrança por cliente. 

Os tipos de ação podem ser criados antes ou depois da data de vencimento da fatura, com base na configuração exibida na coluna **Dias em relação à data de vencimento da fatura**.

Quando você selecionar um tipo de ação de email, o destinatário será usado para definir se é um contato de cliente, grupo de vendas ou agente de cobranças. Em seguida, o valor no campo **Contato de finalidade comercial** determinará qual contato da conta desse cliente receberá a comunicação.

## <a name="business-document-details"></a>Detalhes do documento comercial
Os detalhes do documento comercial variarão com base no tipo de ação selecionado nos detalhes do processo.  Quando o tipo de ação for uma atividade, os detalhes do modelo de atividade serão exibidos.  Esses detalhes incluem o nome do modelo de atividade, o tipo de atividade que será criado, a finalidade da atividade, o número de dias agendados para concluir a atividade e os detalhes da atividade.  Essa atividade será vinculada à fatura principal que informa ao destinatário a ação necessária para concluí-la.

Se o tipo de ação for um email nos detalhes do processo, essa seção conterá duas Guias Rápidas.  A primeira é usada para definir a ID do modelo, a descrição do email, o idioma padrão, o nome de usuário que será atribuído às mensagens de email enviadas automaticamente e o endereço de email dos remetentes associados. A segunda permitirá que o corpo do email seja criado após os valores nos campos **Idioma** e **Assunto** serem salvos selecionando **Editar**.  Isso abrirá uma janela que permite carregar conteúdo HTML. Você também pode digitar a mensagem que é criada manualmente na caixa inferior esquerda da janela.  

> [!Note]
> Um email do Outlook pode ser salvo com o corpo desejado da comunicação no formato HTML. Em seguida, ele pode ser carregado para implementar o modelo. <br> <br> Se o tipo de ação da carta de cobrança for selecionado, não haverá uma seção de detalhes do documento comercial no formulário de configuração.


## <a name="fasttab-reference"></a>Referência de Guias Rápidas
As tabelas a seguir listam as páginas e os campos dos quais as Guias Rápidas especificadas podem ser acessadas, juntamente com uma descrição das informações nessa guia. 

### <a name="process-hierarchy"></a>Hierarquia de processos

|     Página                                                  |     Campo                         |     descrição                           |
| --------------------------------------------------------  |-------------------------------    |---------------------------------------    |
|     Configuração do processo de cobranças <br> Automação de processos       |                                   |     Crie e gerencie processos de cobranças baseados em atribuições de grupos de clientes.                                                                                                                             |
|     Configuração do processo de cobranças <br> Automação de processos       |     Hierarquia                     |     Define a prioridade da automação de processos para atribuir um cliente caso ele pertença a vários grupos.                                                                                                   |
|     Configuração do processo de cobranças <br> Automação de processos       |     ID do grupo                       |     Consultas que definem um grupo de registros de clientes.                                                                                                                                                        |
|     Configuração do processo de cobranças <br> Automação de processos       |     Dias silenciosos                    |     Limite a frequência com que uma etapa do processo pode ser concluída. Por exemplo, se dois dias silenciosos forem definidos, a próxima etapa do processo não ocorrerá por pelo menos dois dias caso a fatura principal seja alterada.     |
|     Configuração do processo de cobranças <br> Automação de processos       |     Excluir do Processo        |     Selecionar **Saldo de classificação por vencimento do cliente menor que** ou **Valor da fatura menor que** excluirá um cliente da automação de processos se os critérios de valor não forem atendidos.                                   |

### <a name="process-details"></a>Detalhes do processo
|     Página                                                  |     Campo                                         |      descrição                  |
|--------------------------------------------------------   |-----------------------------------------------    |----------------------------   |
|     Configuração do processo de cobranças <br> Automação de processos       |                                                   |     Defina as etapas executadas com base na fatura principal.                                                                                                |
|                                                           |     descrição                                   |     Campo de texto livre usado para fornecer um nome e/ou descrição da etapa.                                                                           |
|                                                           |     Tipo de ação                                   |     Atividade, email ou carta de cobrança que serão criados pela etapa do processo.                                                                     |
|                                                           |     Documento comercial                           |     Define o modelo de atividade ou email usado durante a etapa do processo.                                                                        |
|                                                           |     Quando                                          |     Define se a etapa do processo ocorrerá antes ou depois da data de vencimento da fatura principal, juntamente com o campo **Dias em relação à data de vencimento da fatura**.        |
|                                                           |     Dias em relação à data de vencimento da fatura        |     Juntamente com o campo **Quando**, ele identifica o momento da etapa do processo.                                                                          |
|                                                           |     Destinatário                                     |     Identifica se um email será enviado a um contato de Cliente, Grupo de vendas ou Agente de Cobranças.                                                   |
|                                                           |     Contato de finalidade comercial                    |     Determina qual endereço de email do destinatário é usado em comunicações por email.                                                                                 |

### <a name="business-process-activity-template-details"></a>Detalhes do modelo de atividade de processo empresarial 
|     Página                                                  |     Campo                     |      descrição                  |
|--------------------------------------------------------   |----------------------------   |-------------------------  |
|     Configuração do processo de cobranças <br> Automação de processos       |                               |     Seção do processo de configuração que identifica os detalhes do modelo de atividade.                                                                      |
|     Configuração do processo de cobranças <br> Automação de processos       |     Modelo de atividade       |     Identifica o tipo, a finalidade, o número de dias para conclusão e fornece detalhes sobre a atividade que será criada durante uma etapa do processo de atividade.       |

### <a name="business-document-email-template-details"></a>Detalhes do modelo de email do documento comercial 
|     Página                                                  |     Campo     |      descrição                  |
|--------------------------------------------------------   |-------------- |-----------------------------  |
|     Configuração do processo de cobranças <br> Automação de processos       |               |     Identifica a descrição do email, o idioma padrão, o nome dos remetentes e o endereço de email que será criado durante uma etapa do processo de email.        |


### <a name="collections-history"></a>Histórico de cobranças 
|     Página                              |     Campo     |      descrição                                                          |
|------------------------------------   |-------------- |---------------------------------------------------------------------  |
|     Configuração do processo de cobranças       |               |     Veja o histórico recente da hierarquia de processos selecionada.     |

### <a name="collection-process-assignment"></a>Atribuição do processo de cobrança
|     Página                              |     Campo     |      descrição                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|     Configuração do processo de cobranças       |               |     Veja os clientes atribuídos a um processo de cobranças.  
|     Atribuição manual               |               |     Veja os clientes que foram atribuídos manualmente a um processo ou selecione clientes para serem atribuídos a um processo. |
|     Visualizar atribuição de processo      |               |     Visualize os clientes que serão atribuídos a uma estratégia quando ela for executada.   |
|     Visualizar atribuição de cliente     |               |     Veja a estratégia atribuída a um cliente específico.    |
 
### <a name="parameters"></a>Parâmetros
|     Página                                                                  |     Campo                                             |      descrição                              |
|-------------------------------------------------------------------------- |------------------------------------------------------ |-------------------------------------  |
|     Parâmetros de contas a receber > Automação do processo de cobranças     |     Porcentagem de clientes por tarefa em lotes          |     Configuração para determinar o número de tarefas em lotes por processo de automação.                                          |
|     Parâmetros de contas a receber > Automação do processo de cobranças     |     Lançar Cartas de cobrança automaticamente           |     Os tipos de ação da carta de cobrança lançarão a carta durante a automação.                                      |
|     Parâmetros de contas a receber > Automação do processo de cobranças     |     Criar atividades para automação                |     Crie e feche atividades para tipos de ação não relacionados a atividades a fim de exibir todas as etapas automatizadas executadas em uma conta.        |
|     Parâmetros de contas a receber > Automação do processo de cobranças     |     Dias para manter a automação do processo de cobranças     |     Define o número de dias que o histórico de cobranças é armazenado.                                                       |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]