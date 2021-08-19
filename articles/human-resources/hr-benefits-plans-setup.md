---
title: Criar um plano de benefícios
description: Configure planos de benefícios no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 03/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitPlanListPage, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4219c59141a0664e776f1ab099288a7b2db9139d83e1e5bfab7f7b2fbca128a8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731334"
---
# <a name="create-a-benefit-plan"></a>Criar um plano de benefícios

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo mostra como configurar planos de benefícios no Dynamics 365 Human Resources.

1. No espaço de trabalho **Gerenciamento de benefícios** em **Planos** , selecione **Planos de benefícios**.

2. Selecione **Novo**.

3. Na guia **Geral**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Plano** | Um identificador exclusivo do plano. |
   | **Descrição** | Uma descrição do plano. |
   | **Tipo de plano** | Ao criar um plano, você precisa especificar o tipo de plano. Um tipo de plano é um agrupamento de alto nível de tipos específicos de benefícios. Cada tipo de plano especifica se um funcionário pode se inscrever em vários planos desse tipo, especifica se os contatos são beneficiários ou dependentes e define opções de cobertura. É possível criar tipos de planos personalizados para atender às necessidades de suas ofertas de benefícios. Os principais tipos de plano de benefícios são: <ul><li>401K</li><li>Morte ou invalidez por acidente</li><li>Odontológico</li><li>Bem-estar</li><li>FSA</li><li>Vida</li><li>Incapacidade duradoura</li><li>Médico</li><li>Folga remunerada</li><li>Incapacidade temporária</li><li>Oftalmológico</li></ul> |
   | **Código do tipo de plano** | O código do tipo de plano do tipo de plano. |
   | **Programa** | Especifica um programa ao qual atribuir opcionalmente o plano. |
   | **Pacote** | Especifica um pacote ao qual atribuir opcionalmente o plano. |
   | **Mestre** | Especifica se o plano é o plano mestre no pacote ao qual está atribuído. |
   | **Válido a partir da data e hora** | A data e a hora em que o plano tem início. O valor padrão é a data atual do sistema. |
   | **Válido até a data e hora** | A data e a hora em que o plano é encerrado. O valor padrão é 12/31/2154, o que significa nunca. |

4. Na guia **Configuração**, especifique valores para os seguintes campos, dependendo do tipo de plano que você está criando:

   | Tipo de plano | Campo | Descrição |
   | --- | --- | --- |
   | Médico (médico, odontológico, oftalmológico, HMO) | COBRA | Especifica se o plano é qualificado para COBRA (Consolidated Omnibus Budget Reconciliation Act). |
   | Médico (médico, odontológico, oftalmológico, HMO) | HIPAA | Especifica se o plano é qualificado para HIPAA (Health Insurance Portability and Accountability Act). |
   | Médico (médico, odontológico, oftalmológico, HMO)<br><br>Outro (Folga remunerada, Bem-estar)<br><br>Outro<br><br>Incapacidade duradoura<br><br>Morte ou invalidez por acidente (vida básica, vida voluntária)<br><br>Poupança (por exemplo, 401(k))<br><br>FSA | Dedução antes do imposto qualificada | Especifica se as contribuições podem ser feitas no plano antes da aplicação dos impostos. |
   | Médico (médico, odontológico, oftalmológico, HMO)<br><br>Outro (Folga remunerada, Bem-estar)<br><br>Incapacidade duradoura<br><br>Morte ou invalidez por acidente (vida básica, vida voluntária)<br><br>Poupança (por exemplo, 401(k))<br><br>FSA | Dedução depois do imposto qualificada | Especifica se as contribuições podem ser feitas no plano depois da aplicação dos impostos. |
   | Médico (médico, odontológico, oftalmológico, HMO)<br><br>Outro (Folga remunerada, Bem-estar)<br><br>Incapacidade duradoura<br><br>Morte ou invalidez por acidente (vida básica, vida voluntária)<br><br>Poupança (por exemplo, 401(k))<br><br>FSA | Parceiro | Especifica quem contribui para o plano – o funcionário, o empregador ou ambos. |
   | Incapacidade duradoura<br><br>Morte ou invalidez por acidente (vida básica, vida voluntária) | Cobertura mínima | A quantidade mínima de cobertura de seguro necessária para o plano. |
   | Incapacidade duradoura<br><br>Morte ou invalidez por acidente (vida básica, vida voluntária) | Cobertura máxima | A quantidade máxima de cobertura de seguro necessária para o plano. |
   | Incapacidade duradoura<br><br>Morte ou invalidez por acidente (vida básica, vida voluntária) | Usar incrementos da cobertura | Especifica se é necessário validar se o valor da cobertura corresponde a um valor incremental válido. |
   | Incapacidade duradoura<br><br>Morte ou invalidez por acidente (vida básica, vida voluntária) | Valor incremental | A quantia incremental de cobertura de seguro para o plano. Por exemplo, se o valor incremental for 1.000, um funcionário não pode ter US$ 200.500 de seguro; seria preciso arredondar para US$ 201.000 ou US$ 200.000. |
   | Incapacidade duradoura<br><br>Morte ou invalidez por acidente (vida básica, vida voluntária) | Direção incremental | Especifica a direção do arredondamento – para mais ou para menos – quando o valor da cobertura não atender o valor incremental. |
   | Morte ou invalidez por acidente (vida básica, vida voluntária) | Evidência de segurabilidade | Especifica se um funcionário deve fornecer evidências de segurabilidade. |
   | Morte ou invalidez por acidente (vida básica, vida voluntária) | Valor | O valor na moeda contábil. Este campo estará ativo apenas se a caixa de seleção Evidência de segurabilidade estiver marcada. |
   | Poupança (por exemplo, 401(k))<br><br>FSA | Contribuição anual mínima | O valor mínimo de contribuição necessário para o plano. |
   | Poupança (por exemplo, 401(k))<br><br>FSA | Contribuição anual máxima | O valor máximo de contribuição necessário para o plano. |
   | Poupança (por exemplo, 401(k)) | Valor anual máximo do empregador | O valor máximo que um empregador pode contribuir para um plano de economia de funcionários durante um período de benefício. Você deve marcar a caixa de seleção Correspondência do empregador para usar esse campo. |
   | Poupança (por exemplo, 401(k)) | Correspondência do empregador | Especifica se o empregador contribui para um plano de economia de funcionários. |
   | Poupança (por exemplo, 401(k)) | Percentual de correlação do empregador | A porcentagem de uma contribuição de funcionário à qual o empregador corresponderá. |
   | Poupança (por exemplo, 401(k)) | Limite de correlação do empregador | A porcentagem máxima que o empregador corresponderá. Por exemplo, se um empregador corresponder 100% das contribuições dos funcionários até 6% do salário do funcionário, o limite de correspondência do empregador será de 6%. |

5. Na guia **Configuração**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Permitir/continuar inscrição** | Especifica se os funcionários podem se inscrever no plano se atenderem aos requisitos de qualificação.</br></br>Se estiver definido como Não, o plano não estará disponível para os funcionários quando você processar a qualificação. |
   | **Inscrição automática do ano anterior** | Especifica se um funcionário qualificado deve ser inscrito automaticamente no plano se ele estava inscrito no ano anterior. |
   | **Inscrição automática por padrão** | Especifica se o plano de inscrição deve ser selecionado por padrão. Como o plano não é obrigatório, o funcionário pode alterar a seleção padrão. |
   | **Fechado para novas inscrições** | Especifica se o plano deve ser restringido apenas aos funcionários qualificados inscritos no plano no ano anterior. |
   | **Plano obrigatório** | Especifica se os funcionários devem ser inscritos automaticamente no plano. Os funcionários não podem alterar a seleção de inscrição. |
   | **Data de início** | A data em que o plano foi criado na empresa. |
   | **Conta do fornecedor** (fornecedor de benefícios) | O fornecedor ao qual a empresa paga prêmios pelo plano. |
   | **Nome** (fornecedor de benefícios) | O nome do fornecedor. |
   | **Referência do fornecedor** (fornecedor de benefícios) | A referência do fornecedor para o plano. Por exemplo, o número do plano de grupo da empresa. |
   | **Referência alternativa** (fornecedor de benefícios) | A referência alternativa do fornecedor para o plano. Por exemplo, o número da conta da empresa. |
   | **Moeda** (fornecedor de benefícios) | A moeda usada para pagar prêmios ao fornecedor. |
   | **Conta de despesa** (fornecedor de benefícios) | A conta contábil que é usada como conta de despesa para os prêmios do plano. |
   | **Conta do fornecedor** (administrador de benefícios) | O fornecedor que a empresa paga para administrar o plano. Se o plano for autoadministrado, deixe esse campo em branco. |
   | **Nome** (administrador de benefícios) | O nome do fornecedor do administrador de benefícios. |
   | **Referência de fornecedor** (administrador de benefícios) | A referência do fornecedor do administrador para o plano. |
   | **Referência alternativa** (administrador de benefícios) | A referência alternativa do fornecedor do administrador para o plano. |
   | **Moeda** (administrador de benefícios) | A moeda usada para pagar o administrador de benefícios. |
   | **Conta de despesa** (administrador de benefícios) | A conta contábil que é usada como conta de despesa para os custos associados à administração do plano. |

6. Na guia **Filtros**, filtre conforme necessário. Você pode filtrar pelos seguintes campos:

   - **Unidade de negócios**
   - **Departamento**
   - **Pessoa jurídica em geral**
   - **Local**
   - **Cargo**

7. Na guia **Regras de qualificação**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Número da linha** | O número de linha da regra de qualificação. |
   | **Regra de qualificação** | Uma regra de qualificação a ser aplicada ao plano de benefícios. Essa regra de qualificação será aplicada ao tipo de ação correspondente e associada ao período de espera da cobertura especificado e deduções. |
   | **Tipo de ação** | A ação para aplicar a regra de qualificação a: inscrição de benefícios ou expiração de benefícios. |
   | **Período de espera da cobertura** | Um valor do formulário Períodos de espera. O período de espera da cobertura determina o número de dias ou meses em que um funcionário aguarda a cobertura ou vencimento do benefício, com base nos critérios da regra de qualificação e do tipo de ação. |
   | **Período de espera da dedução** | Um valor do formulário Períodos de espera. O período de espera da dedução determina o número de dias ou meses em que um funcionário aguarda deduções de benefícios de seu salário com base nos critérios da regra de qualificação e do tipo de ação. |

8. Selecione **Salvar**.

## <a name="view-enrolled-workers"></a>Exibir trabalhadores inscritos

Você pode visualizar os trabalhadores inscritos em um plano de benefícios selecionado.

1. No espaço de trabalho **Gerenciamento de benefícios** em **Planos** , selecione **Planos de benefícios**.

2. Na guia **Benefícios** na barra de navegação, selecione **Trabalhadores registrados**.

## <a name="attach-coverage-options"></a>Anexar opções de cobertura

Você pode adicionar opções de cobertura ao plano de benefícios selecionado. Anexar opções de cobertura reúne a configuração de taxa e dedução para uma opção de cobertura.  Exemplo: para um plano médico, o usuário selecionaria uma opção de cobertura familiar.  Eles precisariam selecionar a taxa de família para o plano associado (definido na configuração da taxa) e a dedução para o plano associado (definido na configuração da taxa). Isso fornece o custo para o empregador e funcionário para uma cobertura selecionada. Em seguida, você repetiria o processo para uma cobertura de funcionário+1 ou cobertura de funcionário.

1. No espaço de trabalho **Gerenciamento de benefícios** em **Planos** , selecione **Planos de benefícios**.

2. Na guia **Benefícios** na barra de navegação, selecione **Anexar opções de cobertura**.

## <a name="override-eligibility-rules"></a>Substituir regras de qualificação

Você pode adicionar trabalhadores a um plano como exceções às regras de qualificação. Cada trabalhador que você adicionar será qualificado para o plano de benefícios.

1. No espaço de trabalho **Gerenciamento de benefícios** em **Planos** , selecione **Planos de benefícios**.

2. Na guia **Benefícios** na barra de navegação, selecione **Substituir regra de elegibilidade**.

## <a name="view-attached-periods"></a>Exibir períodos anexados

Você pode exibir uma lista dos períodos de benefícios disponíveis.

1. No espaço de trabalho **Gerenciamento de benefícios** em **Planos** , selecione **Planos de benefícios**.

2. Selecione a guia **Períodos** na barra de navegação.

## <a name="view-plan-description"></a>Exibir descrição do plano

Você pode fornecer uma descrição do plano para ajudar os funcionários com suas seleções de benefícios. A descrição do plano inserida aqui é exibida no Autoatendimento para funcionários ao passar o mouse sobre o plano na lista de opções de cobertura.

1. No espaço de trabalho **Gerenciamento de benefícios** em **Planos** , selecione **Planos de benefícios**.

2. Na guia **Benefícios** na barra de navegação, selecione **Descrição do plano**.

## <a name="view-flex-credit-programs"></a>Exibir programas de crédito flexível

1. No espaço de trabalho **Gerenciamento de benefícios** em **Planos** , selecione **Planos de benefícios**.

2. Na guia **Benefícios** na barra de navegação, selecione **Programas de crédito flexíveis**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]