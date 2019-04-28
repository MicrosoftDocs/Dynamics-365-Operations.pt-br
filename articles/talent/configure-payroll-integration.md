---
title: Configurar a integração da folha de pagamento entre o Talent e o Dayforce
description: Este tópico explica como configurar a integração entre o Microsoft Dynamics 365 for Talent e o Ceridian Dayforce para processar um ciclo de pagamento.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9a88bf61dbb12520b555ceb7363b1c646d95386e
ms.sourcegitcommit: 204e4554e409c39fbbf7b273ad138ce2809931a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2019
ms.locfileid: "898435"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="b571f-103">Configurar a integração da folha de pagamento entre o Talent e o Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b571f-104">A integração entre o Microsoft Dynamics 365 for Talent e o Ceridian Dayforce depende de várias etapas de configuração descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b571f-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="b571f-105">Você deve configurar a integração no Talent e no Dayforce antes de poder processar uma execução de pagamento.</span><span class="sxs-lookup"><span data-stu-id="b571f-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="b571f-106">Ao usar um serviço como o Dayforce para concluir execuções de pagamento, é necessário ativar a integração no Talent.</span><span class="sxs-lookup"><span data-stu-id="b571f-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="b571f-107">A integração requer dados específicos do Talent.</span><span class="sxs-lookup"><span data-stu-id="b571f-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="b571f-108">Portanto, você deve verificar se os dados mapeados para o Dayforce estão configurados no Talent de forma compatível com a integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="b571f-109">A integração usa as seguintes categorias amplas de dados:</span><span class="sxs-lookup"><span data-stu-id="b571f-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="b571f-110">Dados de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="b571f-110">Human resources data</span></span>
- <span data-ttu-id="b571f-111">Dados de remuneração</span><span class="sxs-lookup"><span data-stu-id="b571f-111">Compensation data</span></span>
- <span data-ttu-id="b571f-112">Dados da folha de pagamento, como ciclos de pagamento, períodos de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="b571f-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="b571f-113">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-113">Worker data</span></span>

<span data-ttu-id="b571f-114">Este tópico descreve as etapas que você deve seguir para ativar a integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="b571f-115">Também explica os tipos de dados e os detalhes de configuração que a integração requer.</span><span class="sxs-lookup"><span data-stu-id="b571f-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="b571f-116">Habilitar a integração</span><span class="sxs-lookup"><span data-stu-id="b571f-116">Enable the integration</span></span>

<span data-ttu-id="b571f-117">No Talent, você deve ativar a integração e inserir as informações de configuração para se conectar ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="b571f-118">Para que a transação da contabilidade que for produzida seja importada para o Microsoft Dynamics 365 for Finance and Operations, também é preciso configurar uma conta de armazenamento do Microsoft Azure e inserir a cadeia de conexão do Armazenamento do Azure no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b571f-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="b571f-119">Para ativar a integração no Talent, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="b571f-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="b571f-120">Na página **Administração do sistema**, selecione **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="b571f-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="b571f-121">Digite o ponto de extremidade seguro do File Transfer Protocol (FTP) e o caminho seguro da pasta FTP.</span><span class="sxs-lookup"><span data-stu-id="b571f-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="b571f-122">Digite o nome e a senha do usuário que acessará o ponto de extremidade e o caminho da pasta seguros do FTP.</span><span class="sxs-lookup"><span data-stu-id="b571f-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="b571f-123">Teste a conexão, conforme necessário, e defina a opção **Habilitar integração da folha de pagamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b571f-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="b571f-124">Quando a integração é ativada, o pacote e os arquivos de exportação de dados são criados e a frequência é configurada.</span><span class="sxs-lookup"><span data-stu-id="b571f-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="b571f-125">Você pode alterar essa frequência conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b571f-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="b571f-126">Para obter mais informações sobre as contas de armazenamento do Azure e as cadeias de conexão do Armazenamento do Azure, consulte os seguintes tópicos do Azure:</span><span class="sxs-lookup"><span data-stu-id="b571f-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="b571f-127">Sobre as contas de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="b571f-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="b571f-128">Configurar cadeias de conexão do Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="b571f-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="b571f-129">Configurar seus dados</span><span class="sxs-lookup"><span data-stu-id="b571f-129">Configure your data</span></span> 

<span data-ttu-id="b571f-130">Para processar a folha de pagamento, você deve configurar dados de RH no Talent.</span><span class="sxs-lookup"><span data-stu-id="b571f-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="b571f-131">Você deve configurar dados organizacionais, como cargos e posições, juntamente com informações sobre benefícios e remuneração.</span><span class="sxs-lookup"><span data-stu-id="b571f-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="b571f-132">Esses dados fornecem as informações de emprego, pagamento e dedução necessárias para gerar o pagamento do empregado.</span><span class="sxs-lookup"><span data-stu-id="b571f-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="b571f-133">Dados de RH</span><span class="sxs-lookup"><span data-stu-id="b571f-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="b571f-134">Benefícios</span><span class="sxs-lookup"><span data-stu-id="b571f-134">Benefits</span></span> 

<span data-ttu-id="b571f-135">O RH fornece ferramentas para a configuração e manutenção dos benefícios, deduções e planos de remuneração do trabalhador que uma organização oferece ou processa para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="b571f-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="b571f-136">Ao criar benefícios, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="b571f-137">Planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="b571f-137">Benefit plans</span></span>

- <span data-ttu-id="b571f-138">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-138">Plan (required)</span></span>
- <span data-ttu-id="b571f-139">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-139">Type (required)</span></span>
- <span data-ttu-id="b571f-140">Impacto da folha de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-140">Payroll impact (required)</span></span>
- <span data-ttu-id="b571f-141">Recuperar atrasos de pagamento</span><span class="sxs-lookup"><span data-stu-id="b571f-141">Recover arrears</span></span>
- <span data-ttu-id="b571f-142">Método de dedução</span><span class="sxs-lookup"><span data-stu-id="b571f-142">Deduction method</span></span>
- <span data-ttu-id="b571f-143">Prioridade da dedução</span><span class="sxs-lookup"><span data-stu-id="b571f-143">Deduction priority</span></span>
- <span data-ttu-id="b571f-144">Limitar período</span><span class="sxs-lookup"><span data-stu-id="b571f-144">Limit period</span></span>
- <span data-ttu-id="b571f-145">Valor de limite</span><span class="sxs-lookup"><span data-stu-id="b571f-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="b571f-146">Benefícios</span><span class="sxs-lookup"><span data-stu-id="b571f-146">Benefits</span></span>

- <span data-ttu-id="b571f-147">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-147">Plan (required)</span></span>
- <span data-ttu-id="b571f-148">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-148">Type (required)</span></span>
- <span data-ttu-id="b571f-149">Opção (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-149">Option (required)</span></span>
- <span data-ttu-id="b571f-150">ID do benefício (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-150">Benefit ID (required)</span></span>
- <span data-ttu-id="b571f-151">Frequência</span><span class="sxs-lookup"><span data-stu-id="b571f-151">Frequency</span></span>
- <span data-ttu-id="b571f-152">Base</span><span class="sxs-lookup"><span data-stu-id="b571f-152">Basis</span></span>
- <span data-ttu-id="b571f-153">Valor ou taxa</span><span class="sxs-lookup"><span data-stu-id="b571f-153">Amount or rate</span></span>
- <span data-ttu-id="b571f-154">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="b571f-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="b571f-155">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="b571f-155">Supported frequencies</span></span> 

- <span data-ttu-id="b571f-156">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="b571f-156">Weekly</span></span>
- <span data-ttu-id="b571f-157">Por quinzena</span><span class="sxs-lookup"><span data-stu-id="b571f-157">Bi-weekly</span></span>
- <span data-ttu-id="b571f-158">Quinzenal</span><span class="sxs-lookup"><span data-stu-id="b571f-158">Semi-monthly</span></span>
- <span data-ttu-id="b571f-159">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="b571f-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="b571f-160">Bases com suporte</span><span class="sxs-lookup"><span data-stu-id="b571f-160">Supported bases</span></span> 

- <span data-ttu-id="b571f-161">Valor fixo</span><span class="sxs-lookup"><span data-stu-id="b571f-161">Fixed amount</span></span>
- <span data-ttu-id="b571f-162">Percentual de ganhos</span><span class="sxs-lookup"><span data-stu-id="b571f-162">Percent of earnings</span></span>
- <span data-ttu-id="b571f-163">Horas produtivas</span><span class="sxs-lookup"><span data-stu-id="b571f-163">Productive hours</span></span>

<span data-ttu-id="b571f-164">O Dayforce cria as deduções a seguir, com base no impacto da folha de pagamento definido no plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="b571f-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="b571f-165">Seleção no Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-165">Selection in Talent</span></span>        | <span data-ttu-id="b571f-166">Resultado no Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="b571f-167">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-167">None</span></span>                       | <span data-ttu-id="b571f-168">Nenhuma dedução é criada.</span><span class="sxs-lookup"><span data-stu-id="b571f-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="b571f-169">Somente dedução</span><span class="sxs-lookup"><span data-stu-id="b571f-169">Deduction only</span></span>             | <span data-ttu-id="b571f-170">Uma dedução de funcionário é criada.</span><span class="sxs-lookup"><span data-stu-id="b571f-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="b571f-171">Somente contribuição</span><span class="sxs-lookup"><span data-stu-id="b571f-171">Contribution only</span></span>          | <span data-ttu-id="b571f-172">Uma dedução de empregador é criada.</span><span class="sxs-lookup"><span data-stu-id="b571f-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="b571f-173">Dedução e contribuição</span><span class="sxs-lookup"><span data-stu-id="b571f-173">Deduction and contribution</span></span> | <span data-ttu-id="b571f-174">Deduções de funcionário e empregador são criadas.</span><span class="sxs-lookup"><span data-stu-id="b571f-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="b571f-175">Para obter mais informações sobre como definir e gerenciar um programa de benefícios, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b571f-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="b571f-176">Entregar um programa de benefícios do funcionário</span><span class="sxs-lookup"><span data-stu-id="b571f-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="b571f-177">Criar um novo benefício</span><span class="sxs-lookup"><span data-stu-id="b571f-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="b571f-178">Definir regras e políticas de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="b571f-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="b571f-179">Inscrever e remover benefícios de trabalhadores</span><span class="sxs-lookup"><span data-stu-id="b571f-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="b571f-180">Remuneração</span><span class="sxs-lookup"><span data-stu-id="b571f-180">Compensation</span></span> 

<span data-ttu-id="b571f-181">O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios.</span><span class="sxs-lookup"><span data-stu-id="b571f-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="b571f-182">Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos.</span><span class="sxs-lookup"><span data-stu-id="b571f-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="b571f-183">O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="b571f-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="b571f-184">O Dayforce usa informações de remuneração para calcular a taxa por hora ou anual de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="b571f-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="b571f-185">Planos de remuneração fixa e conversões de taxa de pagamento são necessários.</span><span class="sxs-lookup"><span data-stu-id="b571f-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="b571f-186">Os funcionários devem estar associados a um plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="b571f-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="b571f-187">Para obter mais informações sobre planos de remuneração, veja os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="b571f-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="b571f-188">Criar planos de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="b571f-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="b571f-189">Criar planos de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="b571f-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="b571f-190">Desenvolver estrutura e planos de remuneração/salário</span><span class="sxs-lookup"><span data-stu-id="b571f-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="b571f-191">Processar remuneração</span><span class="sxs-lookup"><span data-stu-id="b571f-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="b571f-192">Definir processo de remuneração e calcular resultados</span><span class="sxs-lookup"><span data-stu-id="b571f-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="b571f-193">Inscrever um funcionário em um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="b571f-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="b571f-194">Inscrever um funcionário em um plano de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="b571f-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="b571f-195">Trabalhos</span><span class="sxs-lookup"><span data-stu-id="b571f-195">Jobs</span></span> 

<span data-ttu-id="b571f-196">Um trabalho é um conjunto de tarefas e responsabilidades exigidas de uma pessoa que realiza um trabalho.</span><span class="sxs-lookup"><span data-stu-id="b571f-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="b571f-197">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b571f-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="b571f-198">Configurando os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="b571f-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="b571f-199">Definir novos trabalhos</span><span class="sxs-lookup"><span data-stu-id="b571f-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="b571f-200">Posições</span><span class="sxs-lookup"><span data-stu-id="b571f-200">Positions</span></span>

<span data-ttu-id="b571f-201">Um cargo é uma instância individual de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="b571f-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="b571f-202">Por exemplo, a posição "Gerente de vendas (Leste)" é uma das posições associadas ao trabalho "Gerente de vendas".</span><span class="sxs-lookup"><span data-stu-id="b571f-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="b571f-203">Uma posição existe em um departamento.</span><span class="sxs-lookup"><span data-stu-id="b571f-203">A position exists in a department.</span></span> <span data-ttu-id="b571f-204">Apenas um trabalhador pode ser associado a cada posição.</span><span class="sxs-lookup"><span data-stu-id="b571f-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="b571f-205">Considere os seguintes dados e configurações ao configurar as posições:</span><span class="sxs-lookup"><span data-stu-id="b571f-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="b571f-206">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-206">Position (required)</span></span>
- <span data-ttu-id="b571f-207">Descrição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-207">Description (required)</span></span>
- <span data-ttu-id="b571f-208">Trabalho (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-208">Job (required)</span></span>
- <span data-ttu-id="b571f-209">Departamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-209">Department (required)</span></span>
- <span data-ttu-id="b571f-210">Tipo de posição (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-210">Position type (required)</span></span>
- <span data-ttu-id="b571f-211">Equivalente ao horário integral</span><span class="sxs-lookup"><span data-stu-id="b571f-211">Full-time equivalent</span></span>
- <span data-ttu-id="b571f-212">Horas normais anuais (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="b571f-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="b571f-213">Pago por entidade legal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="b571f-214">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-214">Pay cycle (required)</span></span>
- <span data-ttu-id="b571f-215">Dimensão financeira padrão – Centro de custo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="b571f-216">Atribuição do trabalhador – Trabalhador, início da atribuição, fim da atribuição, código de motivo</span><span class="sxs-lookup"><span data-stu-id="b571f-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="b571f-217">Se várias posições no mesmo departamento estiverem associadas ao mesmo trabalho, elas serão consolidadas em uma única posição no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="b571f-218">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b571f-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="b571f-219">Organizar sua força de trabalho usando departamentos, trabalhos e posições</span><span class="sxs-lookup"><span data-stu-id="b571f-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="b571f-220">Configurar posições</span><span class="sxs-lookup"><span data-stu-id="b571f-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="b571f-221">Departamentos</span><span class="sxs-lookup"><span data-stu-id="b571f-221">Departments</span></span>

<span data-ttu-id="b571f-222">Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização.</span><span class="sxs-lookup"><span data-stu-id="b571f-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="b571f-223">Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="b571f-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="b571f-224">Você pode usar departamentos para relatar áreas funcionais.</span><span class="sxs-lookup"><span data-stu-id="b571f-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="b571f-225">Os departamentos podem ter a responsabilidade de lucros e perdas.</span><span class="sxs-lookup"><span data-stu-id="b571f-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="b571f-226">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b571f-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="b571f-227">Criar um departamento e associá-lo à hierarquia de departamentos</span><span class="sxs-lookup"><span data-stu-id="b571f-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="b571f-228">Definir novos departamentos</span><span class="sxs-lookup"><span data-stu-id="b571f-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="b571f-229">Ciclos de pagamento e períodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="b571f-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="b571f-230">Um ciclo de pagamento determina a frequência com que a folha de pagamento é executada e os dias específicos em que os trabalhadores são pagos.</span><span class="sxs-lookup"><span data-stu-id="b571f-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="b571f-231">Por exemplo, um ciclo de pagamento pode ser mensal e os funcionários podem ser pagos no último dia do mês.</span><span class="sxs-lookup"><span data-stu-id="b571f-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="b571f-232">Como alternativa, um ciclo de pagamento pode ser semanal e os funcionários podem ser pagos na terça-feira após o término do período de pagamento.</span><span class="sxs-lookup"><span data-stu-id="b571f-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="b571f-233">Ciclos de pagamento são atribuídos a posições para controlar quando os trabalhadores nessas posições são pagos.</span><span class="sxs-lookup"><span data-stu-id="b571f-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="b571f-234">Após a criação dos ciclos de pagamento, você pode gerar períodos de pagamento para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="b571f-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="b571f-235">Cada período de pagamento inclui uma data de pagamento padrão baseada nas informações que você fornece.</span><span class="sxs-lookup"><span data-stu-id="b571f-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="b571f-236">No entanto, você pode modificar a data de pagamento padrão em um período de pagamento para permitir exceções (por exemplo, quando a data de pagamento cai em um feriado).</span><span class="sxs-lookup"><span data-stu-id="b571f-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="b571f-237">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="b571f-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="b571f-238">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-238">Pay cycle (required)</span></span>
- <span data-ttu-id="b571f-239">Frequência do ciclo de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="b571f-240">Data de início do período (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="b571f-241">Data de pagamento padrão (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="b571f-242">Essas informações são integradas ao Dayforce como grupos de pagamento e são separadas por país ou região para cada ciclo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="b571f-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="b571f-243">Pelo menos um período de pagamento deve ser gerado antes da integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="b571f-244">O Dayforce gera datas de pagamento e calendários do grupo de pagamento, com base na data de início do primeiro período de pagamento e na data de pagamento padrão configurada no Talent.</span><span class="sxs-lookup"><span data-stu-id="b571f-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="b571f-245">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="b571f-245">Earning codes</span></span>

<span data-ttu-id="b571f-246">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="b571f-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="b571f-247">Os códigos têm vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="b571f-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="b571f-248">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="b571f-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="b571f-249">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-249">Earning Code (required)</span></span>
- <span data-ttu-id="b571f-250">descrição</span><span class="sxs-lookup"><span data-stu-id="b571f-250">Description</span></span>
- <span data-ttu-id="b571f-251">Unidade de medida</span><span class="sxs-lookup"><span data-stu-id="b571f-251">Unit of measure</span></span>
- <span data-ttu-id="b571f-252">Produtivo</span><span class="sxs-lookup"><span data-stu-id="b571f-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="b571f-253">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-253">Worker data</span></span>

<span data-ttu-id="b571f-254">Os registros dos vários tipos de trabalhadores que você tem são importantes para o RH e sistemas de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="b571f-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="b571f-255">As informações inseridas podem ser usadas para rastrear trabalhadores e informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="b571f-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="b571f-256">Você pode manter estas informações para trabalhadores:</span><span class="sxs-lookup"><span data-stu-id="b571f-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="b571f-257">**Básicas** – mantenha informações básicas do trabalhador, como informações de contato, demográficas, de identificação, sobre a família, o status de serviço militar, informações de exilado, contatos pessoais e de emergência.</span><span class="sxs-lookup"><span data-stu-id="b571f-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="b571f-258">**Emprego** – mantenha informações sobre o emprego dos trabalhadores, como a afiliação da empresa ou organização, a atribuição de posição, as datas inicial e final, a qualificação para trabalho, o contrato de trabalho, a pensão, férias e as informações de mudança.</span><span class="sxs-lookup"><span data-stu-id="b571f-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="b571f-259">**Licença e ausência** – mantenha informações sobre as ausências dos trabalhadores, como o calendário de trabalho, as transações de ausência e a configuração de ausência.</span><span class="sxs-lookup"><span data-stu-id="b571f-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="b571f-260">**Remuneração e folha de pagamento** – mantenha informações sobre os planos de remuneração e as informações de folha de pagamento de trabalhadores, como o registro do plano, prêmios, o desempenho, a comissão, informações sobre impostos, aposentadoria e deduções do salário.</span><span class="sxs-lookup"><span data-stu-id="b571f-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="b571f-261">Ao inserir informações do trabalhador, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="b571f-262">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="b571f-262">General information</span></span>

- <span data-ttu-id="b571f-263">Número de equipe (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-263">Personnel number (required)</span></span>
- <span data-ttu-id="b571f-264">Nome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-264">First name (required)</span></span>
- <span data-ttu-id="b571f-265">Sobrenome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-265">Last name (required)</span></span>
- <span data-ttu-id="b571f-266">Nome do meio</span><span class="sxs-lookup"><span data-stu-id="b571f-266">Middle name</span></span>
- <span data-ttu-id="b571f-267">Aniversário de tempo de serviço</span><span class="sxs-lookup"><span data-stu-id="b571f-267">Seniority date</span></span>
- <span data-ttu-id="b571f-268">Conhecido como</span><span class="sxs-lookup"><span data-stu-id="b571f-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="b571f-269">Informações pessoais</span><span class="sxs-lookup"><span data-stu-id="b571f-269">Personal information</span></span>

- <span data-ttu-id="b571f-270">Estado civil (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-270">Marital status (required)</span></span>
- <span data-ttu-id="b571f-271">Data de nascimento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-271">Birth date (required)</span></span>
- <span data-ttu-id="b571f-272">Sexo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-272">Gender (required)</span></span>
- <span data-ttu-id="b571f-273">Pessoa portadora de deficiências</span><span class="sxs-lookup"><span data-stu-id="b571f-273">Person with disabilities</span></span>
- <span data-ttu-id="b571f-274">Região do país de nacionalidade (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="b571f-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="b571f-275">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="b571f-275">Address information</span></span>

- <span data-ttu-id="b571f-276">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-276">Primary (required)</span></span>
- <span data-ttu-id="b571f-277">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-277">Country/region (required)</span></span>
- <span data-ttu-id="b571f-278">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-278">Postal code (required)</span></span>
- <span data-ttu-id="b571f-279">Número da rua (obrigatório) (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="b571f-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="b571f-280">Complemento do edifício (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="b571f-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="b571f-281">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-281">City (required)</span></span>
- <span data-ttu-id="b571f-282">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-282">State (required)</span></span>
- <span data-ttu-id="b571f-283">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="b571f-284">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="b571f-284">Contact information</span></span> 

- <span data-ttu-id="b571f-285">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-285">Primary (required)</span></span>
- <span data-ttu-id="b571f-286">Número de contato (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-286">Contact number (required)</span></span>
- <span data-ttu-id="b571f-287">Extensão</span><span class="sxs-lookup"><span data-stu-id="b571f-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="b571f-288">Informações sobre folha de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="b571f-288">Payroll information and earning codes</span></span>

<span data-ttu-id="b571f-289">Os funcionários podem receber ganhos específicos com uma determinada frequência de pagamento e ter um método de pagamento preferencial.</span><span class="sxs-lookup"><span data-stu-id="b571f-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="b571f-290">Os campos a seguir são usados no Dayforce para ajudar a garantir que essas preferências e configurações sejam usadas.</span><span class="sxs-lookup"><span data-stu-id="b571f-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="b571f-291">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="b571f-291">Earning codes</span></span>

- <span data-ttu-id="b571f-292">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-292">Position (required)</span></span>
- <span data-ttu-id="b571f-293">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-293">Earning Code (required)</span></span>
- <span data-ttu-id="b571f-294">Frequência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-294">Frequency (required)</span></span>
- <span data-ttu-id="b571f-295">Valor (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="b571f-296">Informações da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="b571f-296">Payroll information</span></span>

- <span data-ttu-id="b571f-297">Método de Pagamento</span><span class="sxs-lookup"><span data-stu-id="b571f-297">Payment Method</span></span>
- <span data-ttu-id="b571f-298">Região econômica (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-298">Economic Region (required)</span></span>
- <span data-ttu-id="b571f-299">ID de Benefícios do Funcionário</span><span class="sxs-lookup"><span data-stu-id="b571f-299">Employee Benefits ID</span></span>
- <span data-ttu-id="b571f-300">Número de ID nacional (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-300">National ID Number (required)</span></span>
- <span data-ttu-id="b571f-301">Número de serviço militar</span><span class="sxs-lookup"><span data-stu-id="b571f-301">Military Service Number</span></span>
- <span data-ttu-id="b571f-302">ID de turno (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-302">Shift ID (required)</span></span>
- <span data-ttu-id="b571f-303">Número fiscal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-303">Tax Number (required)</span></span>
- <span data-ttu-id="b571f-304">ID do sindicato (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-304">Union ID (required)</span></span>
- <span data-ttu-id="b571f-305">ID do dia útil (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-305">Work Day ID (required)</span></span>
- <span data-ttu-id="b571f-306">Número de autorização de trabalho</span><span class="sxs-lookup"><span data-stu-id="b571f-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="b571f-307">Para o método de pagamento, o México permite **Pagamento à vista**, **Cheque** (o cheque físico da empresa) e **Pagamento Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="b571f-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="b571f-308">Se nenhum método de pagamento for especificado, **Cheque** é usado por padrão.</span><span class="sxs-lookup"><span data-stu-id="b571f-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="b571f-309">Detalhes do emprego</span><span class="sxs-lookup"><span data-stu-id="b571f-309">Employment details</span></span>

<span data-ttu-id="b571f-310">O histórico de detalhes de emprego é usado como principal informação para derivar os status de contratação, rescisão e recontratação de um funcionário no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="b571f-311">O Dayforce suporta apenas um registro de emprego ativo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="b571f-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="b571f-312">Data de início do emprego (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-312">Employment start date (required)</span></span>
- <span data-ttu-id="b571f-313">Data final do emprego</span><span class="sxs-lookup"><span data-stu-id="b571f-313">Employment end date</span></span>
- <span data-ttu-id="b571f-314">Data de início</span><span class="sxs-lookup"><span data-stu-id="b571f-314">Start date</span></span>
- <span data-ttu-id="b571f-315">Data inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="b571f-315">Adjusted start date</span></span>
- <span data-ttu-id="b571f-316">Data de rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="b571f-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="b571f-317">Motivo da rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="b571f-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="b571f-318">As principais datas de um funcionário são derivadas usando-se as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="b571f-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="b571f-319">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-319">Talent</span></span>                | <span data-ttu-id="b571f-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b571f-321">Data de contratação mais recente</span><span class="sxs-lookup"><span data-stu-id="b571f-321">Most recent hire date</span></span> | <span data-ttu-id="b571f-322">Início de emprego do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="b571f-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="b571f-323">Data da rescisão</span><span class="sxs-lookup"><span data-stu-id="b571f-323">Termination date</span></span>      | <span data-ttu-id="b571f-324">Data de rescisão do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="b571f-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="b571f-325">Data de início</span><span class="sxs-lookup"><span data-stu-id="b571f-325">Start date</span></span>            | <span data-ttu-id="b571f-326">Data de início ajustada, data de início ou início de emprego do registro histórico de emprego não ativo atual</span><span class="sxs-lookup"><span data-stu-id="b571f-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="b571f-327">Data original de contratação</span><span class="sxs-lookup"><span data-stu-id="b571f-327">Original hire date</span></span>    | <span data-ttu-id="b571f-328">Início de emprego do registro histórico de emprego mais antigo</span><span class="sxs-lookup"><span data-stu-id="b571f-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="b571f-329">Remuneração</span><span class="sxs-lookup"><span data-stu-id="b571f-329">Compensation</span></span>

<span data-ttu-id="b571f-330">Um plano de remuneração fixa deve estar associado à posição principal de cada funcionário durante um período de emprego.</span><span class="sxs-lookup"><span data-stu-id="b571f-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="b571f-331">Esse período tem início na data em que o funcionário foi contratado (ou na data de início do emprego) e continua até a rescisão.</span><span class="sxs-lookup"><span data-stu-id="b571f-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="b571f-332">Data de vigência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-332">Effective Date (required)</span></span>
- <span data-ttu-id="b571f-333">Data de validade</span><span class="sxs-lookup"><span data-stu-id="b571f-333">Expiration date</span></span>
- <span data-ttu-id="b571f-334">Taxa de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-334">Pay Rate (required)</span></span>
- <span data-ttu-id="b571f-335">Conversões de taxa de pagamento (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="b571f-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="b571f-336">Equivalente anual (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="b571f-337">Equivalente por hora (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="b571f-338">Se um funcionário por hora tiver várias posições, a remuneração fixa da posição principal é importada para o Dayforce como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="b571f-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="b571f-339">Para posições não principais, a taxa por hora é salva na posição correspondente no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="b571f-340">Se um funcionário assalariado tiver várias posições, a taxa acumulada de horas e o salário anual em todas as posições ativas serão derivados e usados como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="b571f-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="b571f-341">Números de identificação</span><span class="sxs-lookup"><span data-stu-id="b571f-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="b571f-342">Cadastro de Pessoa Física (CPF)</span><span class="sxs-lookup"><span data-stu-id="b571f-342">Social Security identifier</span></span> 

<span data-ttu-id="b571f-343">Todos os funcionários devem ter um identificador principal.</span><span class="sxs-lookup"><span data-stu-id="b571f-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="b571f-344">Esse identificador deve ser o tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="b571f-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="b571f-345">No Dayforce, ele é derivado automaticamente como o identificador de pessoa física do funcionário necessário para a contratação.</span><span class="sxs-lookup"><span data-stu-id="b571f-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="b571f-346">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-346">Primary (required)</span></span>
- <span data-ttu-id="b571f-347">Tipo de identificação = "CPF"</span><span class="sxs-lookup"><span data-stu-id="b571f-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="b571f-348">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="b571f-348">Issued Date</span></span>
- <span data-ttu-id="b571f-349">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="b571f-349">Expiration Date</span></span>

<span data-ttu-id="b571f-350">Os funcionários podem declarar vários números de identificação do tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="b571f-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="b571f-351">No entanto, somente o registro marcado como **Principal** será integrado ao Dayforce, independentemente de o número estar ativo ou expirado.</span><span class="sxs-lookup"><span data-stu-id="b571f-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="b571f-352">Contas bancárias e pagamentos</span><span class="sxs-lookup"><span data-stu-id="b571f-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="b571f-353">Informações de conta bancária válidas devem ser inseridas para qualquer funcionário que opte por ser pago por meio de transferências bancárias.</span><span class="sxs-lookup"><span data-stu-id="b571f-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="b571f-354">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-354">Talent</span></span>                         | <span data-ttu-id="b571f-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b571f-356">Número da conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="b571f-357">Código SWIFT (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-357">SWIFT code (required)</span></span>          | <span data-ttu-id="b571f-358">Campo **ID do banco** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="b571f-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="b571f-359">Número da agência (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="b571f-360">Tipo de conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-360">Bank account type (required)</span></span>   | <span data-ttu-id="b571f-361">Campo **Tipo de conta** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="b571f-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="b571f-362">Os valores com suporte incluem **Movimento** e **Folha de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="b571f-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="b571f-363">Os funcionários que optarem por serem pagos por meio de transferências bancárias deverão fornecer um link para uma conta de pendência em uma entidade legal que tenha seu endereço principal no México e esteja associada a uma conta bancária válida de um banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="b571f-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="b571f-364">Todas as outras contas que não são de pendência são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="b571f-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="b571f-365">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="b571f-365">Address information</span></span>

<span data-ttu-id="b571f-366">Todos os funcionários devem ter um local principal.</span><span class="sxs-lookup"><span data-stu-id="b571f-366">Every employee must have one primary location.</span></span> <span data-ttu-id="b571f-367">No Dayforce, esse local é usado para determinar a residência principal do funcionário para fins fiscais.</span><span class="sxs-lookup"><span data-stu-id="b571f-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="b571f-368">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-368">Primary (required)</span></span>
- <span data-ttu-id="b571f-369">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-369">Country/region (required)</span></span>
- <span data-ttu-id="b571f-370">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="b571f-371">Rua (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-371">Street (required)</span></span>
- <span data-ttu-id="b571f-372">Número da rua (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-372">Street Number (required)</span></span>
- <span data-ttu-id="b571f-373">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="b571f-373">Building Complement</span></span>
- <span data-ttu-id="b571f-374">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-374">City (required)</span></span>
- <span data-ttu-id="b571f-375">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-375">State (required)</span></span>
- <span data-ttu-id="b571f-376">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="b571f-377">Configurar seus dados para gerar folha de pagamento nos Estados Unidos e no Canadá</span><span class="sxs-lookup"><span data-stu-id="b571f-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="b571f-378">Se você está gerando pagamento para funcionários nos Estados Unidos e no Canadá, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="b571f-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="b571f-379">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="b571f-379">Departments are required on positions.</span></span>
- <span data-ttu-id="b571f-380">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="b571f-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="b571f-381">Você pode configurar o Talent para exigir que Posições especifique um Departamento.</span><span class="sxs-lookup"><span data-stu-id="b571f-381">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="b571f-382">Para isso, acesse **Posições Compartilhadas de Recursos Humanos > Posições > Exigir departamentos nas posições**.</span><span class="sxs-lookup"><span data-stu-id="b571f-382">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="b571f-383">Recomendamos que esta configuração seja imposta para a integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-383">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="b571f-384">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="b571f-384">Job types</span></span>

<span data-ttu-id="b571f-385">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="b571f-385">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="b571f-386">Os tipos de trabalho são necessários para processar a folha de pagamento nos Estados Unidos e no Canadá.</span><span class="sxs-lookup"><span data-stu-id="b571f-386">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="b571f-387">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="b571f-387">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="b571f-388">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="b571f-388">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="b571f-389">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="b571f-389">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="b571f-390">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b571f-390">Job type</span></span>   | <span data-ttu-id="b571f-391">descrição</span><span class="sxs-lookup"><span data-stu-id="b571f-391">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="b571f-392">Por hora</span><span class="sxs-lookup"><span data-stu-id="b571f-392">Hourly</span></span>     | <span data-ttu-id="b571f-393">Por hora</span><span class="sxs-lookup"><span data-stu-id="b571f-393">Hourly</span></span>      |
| <span data-ttu-id="b571f-394">Assalariado</span><span class="sxs-lookup"><span data-stu-id="b571f-394">Salaried</span></span>   | <span data-ttu-id="b571f-395">Assalariado</span><span class="sxs-lookup"><span data-stu-id="b571f-395">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="b571f-396">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="b571f-396">Position types</span></span> 

<span data-ttu-id="b571f-397">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="b571f-397">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="b571f-398">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="b571f-398">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="b571f-399">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="b571f-399">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="b571f-400">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="b571f-400">Position type</span></span>   | <span data-ttu-id="b571f-401">descrição</span><span class="sxs-lookup"><span data-stu-id="b571f-401">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="b571f-402">Horário integral</span><span class="sxs-lookup"><span data-stu-id="b571f-402">Full-time</span></span>       | <span data-ttu-id="b571f-403">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="b571f-403">Full time employee</span></span> |
| <span data-ttu-id="b571f-404">Meio período</span><span class="sxs-lookup"><span data-stu-id="b571f-404">Part-time</span></span>       | <span data-ttu-id="b571f-405">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="b571f-405">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="b571f-406">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="b571f-406">Reason codes</span></span>

<span data-ttu-id="b571f-407">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="b571f-407">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="b571f-408">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="b571f-408">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="b571f-409">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="b571f-409">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="b571f-410">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="b571f-410">Reason code</span></span>    | <span data-ttu-id="b571f-411">descrição</span><span class="sxs-lookup"><span data-stu-id="b571f-411">Description</span></span>      | <span data-ttu-id="b571f-412">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="b571f-412">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="b571f-413">DEMISSÃO</span><span class="sxs-lookup"><span data-stu-id="b571f-413">RESIGNATION</span></span>    | <span data-ttu-id="b571f-414">Demissão</span><span class="sxs-lookup"><span data-stu-id="b571f-414">Resignation</span></span>      | <span data-ttu-id="b571f-415">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-415">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-416">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="b571f-416">TERMINATION</span></span>    | <span data-ttu-id="b571f-417">Finalização</span><span class="sxs-lookup"><span data-stu-id="b571f-417">Termination</span></span>      | <span data-ttu-id="b571f-418">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-418">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-419">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="b571f-419">RETIREMENT</span></span>     | <span data-ttu-id="b571f-420">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="b571f-420">Retirement</span></span>       | <span data-ttu-id="b571f-421">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-421">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-422">OTHER</span><span class="sxs-lookup"><span data-stu-id="b571f-422">OTHER</span></span>          | <span data-ttu-id="b571f-423">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="b571f-423">Other Reasons</span></span>    | <span data-ttu-id="b571f-424">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-424">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-425">DEATH</span><span class="sxs-lookup"><span data-stu-id="b571f-425">DEATH</span></span>          | <span data-ttu-id="b571f-426">Morte</span><span class="sxs-lookup"><span data-stu-id="b571f-426">Death</span></span>            | <span data-ttu-id="b571f-427">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-427">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-428">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="b571f-428">LEAVEOFABSENCE</span></span> | <span data-ttu-id="b571f-429">Licença</span><span class="sxs-lookup"><span data-stu-id="b571f-429">Leave of Absence</span></span> | <span data-ttu-id="b571f-430">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-430">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-431">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="b571f-431">CONTRACTEND</span></span>    | <span data-ttu-id="b571f-432">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="b571f-432">End of Contract</span></span>  | <span data-ttu-id="b571f-433">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-433">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-434">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="b571f-434">SALARYCHANGE</span></span>   | <span data-ttu-id="b571f-435">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="b571f-435">Change of Salary</span></span> | <span data-ttu-id="b571f-436">Remuneração</span><span class="sxs-lookup"><span data-stu-id="b571f-436">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="b571f-437">Estado civil</span><span class="sxs-lookup"><span data-stu-id="b571f-437">Marital status</span></span>

<span data-ttu-id="b571f-438">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-438">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b571f-439">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-439">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="b571f-440">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-440">Talent</span></span>                 | <span data-ttu-id="b571f-441">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-441">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="b571f-442">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-442">Married</span></span>                | <span data-ttu-id="b571f-443">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-443">Married</span></span>              |
| <span data-ttu-id="b571f-444">Única</span><span class="sxs-lookup"><span data-stu-id="b571f-444">Single</span></span>                 | <span data-ttu-id="b571f-445">Única</span><span class="sxs-lookup"><span data-stu-id="b571f-445">Single</span></span>               |
| <span data-ttu-id="b571f-446">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-446">Widowed</span></span>                | <span data-ttu-id="b571f-447">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-447">Widowed</span></span>              |
| <span data-ttu-id="b571f-448">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-448">Divorced</span></span>               | <span data-ttu-id="b571f-449">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-449">Divorced</span></span>             |
| <span data-ttu-id="b571f-450">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="b571f-450">Registered Partnership</span></span> | <span data-ttu-id="b571f-451">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="b571f-451">Domestic Partnership</span></span> |
| <span data-ttu-id="b571f-452">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-452">None</span></span>                   | <span data-ttu-id="b571f-453">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-453">None</span></span>                 |
| <span data-ttu-id="b571f-454">Coabitando</span><span class="sxs-lookup"><span data-stu-id="b571f-454">Cohabiting</span></span>             | <span data-ttu-id="b571f-455">Coabitando</span><span class="sxs-lookup"><span data-stu-id="b571f-455">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="b571f-456">Sexo</span><span class="sxs-lookup"><span data-stu-id="b571f-456">Gender</span></span>

<span data-ttu-id="b571f-457">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-457">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b571f-458">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-458">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="b571f-459">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-459">Talent</span></span>       | <span data-ttu-id="b571f-460">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-460">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="b571f-461">Masculino</span><span class="sxs-lookup"><span data-stu-id="b571f-461">Male</span></span>         | <span data-ttu-id="b571f-462">Masculino</span><span class="sxs-lookup"><span data-stu-id="b571f-462">Male</span></span>            |
| <span data-ttu-id="b571f-463">Feminino</span><span class="sxs-lookup"><span data-stu-id="b571f-463">Female</span></span>       | <span data-ttu-id="b571f-464">Feminino</span><span class="sxs-lookup"><span data-stu-id="b571f-464">Female</span></span>          |
| <span data-ttu-id="b571f-465">Não específico</span><span class="sxs-lookup"><span data-stu-id="b571f-465">Non-specific</span></span> | <span data-ttu-id="b571f-466">*Sem suporte*</span><span class="sxs-lookup"><span data-stu-id="b571f-466">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="b571f-467">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="b571f-467">Earning codes</span></span>

<span data-ttu-id="b571f-468">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="b571f-468">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="b571f-469">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="b571f-469">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="b571f-470">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="b571f-470">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="b571f-471">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="b571f-471">Supported frequencies</span></span>

- <span data-ttu-id="b571f-472">Todas</span><span class="sxs-lookup"><span data-stu-id="b571f-472">All</span></span>
- <span data-ttu-id="b571f-473">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="b571f-473">EVERYPAY</span></span>
- <span data-ttu-id="b571f-474">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="b571f-474">EACHPAYPERIOD</span></span>
- <span data-ttu-id="b571f-475">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="b571f-475">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="b571f-476">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="b571f-476">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="b571f-477">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-477">1OFMTH</span></span>
- <span data-ttu-id="b571f-478">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-478">LASTOFMTH</span></span>
- <span data-ttu-id="b571f-479">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-479">2OFMTH</span></span>
- <span data-ttu-id="b571f-480">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-480">3OFMTH</span></span>
- <span data-ttu-id="b571f-481">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-481">4OFMTH</span></span>
- <span data-ttu-id="b571f-482">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-482">5OFMTH</span></span>
- <span data-ttu-id="b571f-483">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-483">1N2OFMTH</span></span>
- <span data-ttu-id="b571f-484">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-484">3N4OFMTH</span></span>
- <span data-ttu-id="b571f-485">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-485">1N3OFMTH</span></span>
- <span data-ttu-id="b571f-486">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-486">1N4OFMTH</span></span>
- <span data-ttu-id="b571f-487">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-487">2N3OFMTH</span></span>
- <span data-ttu-id="b571f-488">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-488">2N4OFMTH</span></span>
- <span data-ttu-id="b571f-489">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-489">1N2N3OFMTH</span></span>
- <span data-ttu-id="b571f-490">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-490">1N2N4OFMTH</span></span>
- <span data-ttu-id="b571f-491">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-491">1N3N4OFMTH</span></span>
- <span data-ttu-id="b571f-492">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-492">2N3N4OFMTH</span></span>
- <span data-ttu-id="b571f-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="b571f-494">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="b571f-494">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="b571f-495">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="b571f-495">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="b571f-496">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="b571f-496">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="b571f-497">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="b571f-497">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="b571f-498">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="b571f-498">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="b571f-499">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b571f-499">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="b571f-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b571f-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="b571f-501">Endereços</span><span class="sxs-lookup"><span data-stu-id="b571f-501">Addresses</span></span>

<span data-ttu-id="b571f-502">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="b571f-502">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="b571f-503">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="b571f-503">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="b571f-504">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-504">Talent</span></span>          | <span data-ttu-id="b571f-505">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-505">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="b571f-506">País/Região</span><span class="sxs-lookup"><span data-stu-id="b571f-506">Country/Region</span></span>  | <span data-ttu-id="b571f-507">Código do País</span><span class="sxs-lookup"><span data-stu-id="b571f-507">Country Code</span></span>          |
| <span data-ttu-id="b571f-508">CEP</span><span class="sxs-lookup"><span data-stu-id="b571f-508">Zip/Postal Code</span></span> | <span data-ttu-id="b571f-509">CEP</span><span class="sxs-lookup"><span data-stu-id="b571f-509">Postal Code</span></span>           |
| <span data-ttu-id="b571f-510">Estadual</span><span class="sxs-lookup"><span data-stu-id="b571f-510">State</span></span>           | <span data-ttu-id="b571f-511">Código de estado</span><span class="sxs-lookup"><span data-stu-id="b571f-511">State Code</span></span>            |
| <span data-ttu-id="b571f-512">Cidade</span><span class="sxs-lookup"><span data-stu-id="b571f-512">City</span></span>            | <span data-ttu-id="b571f-513">Cidade</span><span class="sxs-lookup"><span data-stu-id="b571f-513">City</span></span>                  |
| <span data-ttu-id="b571f-514">Região</span><span class="sxs-lookup"><span data-stu-id="b571f-514">County</span></span>          | <span data-ttu-id="b571f-515">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="b571f-515">County (Municipality)</span></span> |
| <span data-ttu-id="b571f-516">Rua</span><span class="sxs-lookup"><span data-stu-id="b571f-516">Street</span></span>          | <span data-ttu-id="b571f-517">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="b571f-517">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="b571f-518">Regiões fiscais</span><span class="sxs-lookup"><span data-stu-id="b571f-518">Tax regions</span></span>

<span data-ttu-id="b571f-519">Regiões fiscais são usadas para determinar os impostos apropriados a serem aplicados durante a geração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="b571f-519">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="b571f-520">As regiões fiscais são mapeadas para o Dayforce como endereços de localização.</span><span class="sxs-lookup"><span data-stu-id="b571f-520">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="b571f-521">A região fiscal padrão deve estar associada à posição ativa do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="b571f-521">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="b571f-522">Região fiscal (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-522">Tax region (required)</span></span>
- <span data-ttu-id="b571f-523">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-523">Country/Region (required)</span></span>
- <span data-ttu-id="b571f-524">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="b571f-524">State (required)</span></span>
- <span data-ttu-id="b571f-525">Região</span><span class="sxs-lookup"><span data-stu-id="b571f-525">County</span></span> 
- <span data-ttu-id="b571f-526">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="b571f-526">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="b571f-527">Configurar seus dados para gerar folha de pagamento no México</span><span class="sxs-lookup"><span data-stu-id="b571f-527">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="b571f-528">Se você está gerando pagamento para funcionários no México, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="b571f-528">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="b571f-529">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="b571f-529">Departments are required on positions.</span></span>
- <span data-ttu-id="b571f-530">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="b571f-530">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="b571f-531">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="b571f-531">Job types</span></span>

<span data-ttu-id="b571f-532">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="b571f-532">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="b571f-533">Tipos de trabalho são necessários para processar a folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="b571f-533">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="b571f-534">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="b571f-534">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="b571f-535">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="b571f-535">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="b571f-536">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="b571f-536">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="b571f-537">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b571f-537">Job type</span></span>   | <span data-ttu-id="b571f-538">descrição</span><span class="sxs-lookup"><span data-stu-id="b571f-538">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="b571f-539">Por hora</span><span class="sxs-lookup"><span data-stu-id="b571f-539">Hourly</span></span>     | <span data-ttu-id="b571f-540">MX por hora</span><span class="sxs-lookup"><span data-stu-id="b571f-540">MX Hourly</span></span>   |
| <span data-ttu-id="b571f-541">Assalariado</span><span class="sxs-lookup"><span data-stu-id="b571f-541">Salaried</span></span>   | <span data-ttu-id="b571f-542">MX assalariado</span><span class="sxs-lookup"><span data-stu-id="b571f-542">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="b571f-543">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="b571f-543">Position types</span></span> 

<span data-ttu-id="b571f-544">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="b571f-544">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="b571f-545">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="b571f-545">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="b571f-546">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="b571f-546">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="b571f-547">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="b571f-547">Position type</span></span>   | <span data-ttu-id="b571f-548">descrição</span><span class="sxs-lookup"><span data-stu-id="b571f-548">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="b571f-549">Horário integral</span><span class="sxs-lookup"><span data-stu-id="b571f-549">Full-time</span></span>       | <span data-ttu-id="b571f-550">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="b571f-550">Full time employee</span></span> |
| <span data-ttu-id="b571f-551">Meio período</span><span class="sxs-lookup"><span data-stu-id="b571f-551">Part-time</span></span>       | <span data-ttu-id="b571f-552">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="b571f-552">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="b571f-553">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="b571f-553">Reason codes</span></span>

<span data-ttu-id="b571f-554">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="b571f-554">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="b571f-555">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="b571f-555">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="b571f-556">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="b571f-556">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="b571f-557">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="b571f-557">Reason code</span></span>            | <span data-ttu-id="b571f-558">descrição</span><span class="sxs-lookup"><span data-stu-id="b571f-558">Description</span></span>                    | <span data-ttu-id="b571f-559">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="b571f-559">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="b571f-560">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="b571f-560">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="b571f-561">Partida antes da primeira folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="b571f-561">Departure before first payroll</span></span> | <span data-ttu-id="b571f-562">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-562">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-563">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="b571f-563">RESIGNATION</span></span>            | <span data-ttu-id="b571f-564">Demissão</span><span class="sxs-lookup"><span data-stu-id="b571f-564">Resignation</span></span>                    | <span data-ttu-id="b571f-565">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-565">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-566">PENSION</span><span class="sxs-lookup"><span data-stu-id="b571f-566">PENSION</span></span>                | <span data-ttu-id="b571f-567">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="b571f-567">Pension</span></span>                        | <span data-ttu-id="b571f-568">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-568">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-569">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="b571f-569">TERMINATION</span></span>            | <span data-ttu-id="b571f-570">Finalização</span><span class="sxs-lookup"><span data-stu-id="b571f-570">Termination</span></span>                    | <span data-ttu-id="b571f-571">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-571">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-572">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="b571f-572">RETIREMENT</span></span>             | <span data-ttu-id="b571f-573">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="b571f-573">Retirement</span></span>                     | <span data-ttu-id="b571f-574">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-574">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-575">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="b571f-575">ABSENTEE</span></span>               | <span data-ttu-id="b571f-576">Absentista</span><span class="sxs-lookup"><span data-stu-id="b571f-576">Absentee</span></span>                       | <span data-ttu-id="b571f-577">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-577">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-578">OTHER</span><span class="sxs-lookup"><span data-stu-id="b571f-578">OTHER</span></span>                  | <span data-ttu-id="b571f-579">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="b571f-579">Other Reasons</span></span>                  | <span data-ttu-id="b571f-580">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-580">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-581">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="b571f-581">CLOSURE</span></span>                | <span data-ttu-id="b571f-582">Fechamento da empresa</span><span class="sxs-lookup"><span data-stu-id="b571f-582">Business Closure</span></span>               | <span data-ttu-id="b571f-583">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-583">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-584">DEATH</span><span class="sxs-lookup"><span data-stu-id="b571f-584">DEATH</span></span>                  | <span data-ttu-id="b571f-585">Morte</span><span class="sxs-lookup"><span data-stu-id="b571f-585">Death</span></span>                          | <span data-ttu-id="b571f-586">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-586">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-587">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="b571f-587">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="b571f-588">Licença</span><span class="sxs-lookup"><span data-stu-id="b571f-588">Leave of Absence</span></span>               | <span data-ttu-id="b571f-589">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-589">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-590">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="b571f-590">CONTRACTEND</span></span>            | <span data-ttu-id="b571f-591">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="b571f-591">End of Contract</span></span>                | <span data-ttu-id="b571f-592">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="b571f-592">Terminate worker</span></span>     |
| <span data-ttu-id="b571f-593">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="b571f-593">SALARYCHANGE</span></span>           | <span data-ttu-id="b571f-594">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="b571f-594">Change of Salary</span></span>               | <span data-ttu-id="b571f-595">Remuneração</span><span class="sxs-lookup"><span data-stu-id="b571f-595">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="b571f-596">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="b571f-596">Terms of employment</span></span>

<span data-ttu-id="b571f-597">Termos de emprego são usados para criar categorias de termos de emprego.</span><span class="sxs-lookup"><span data-stu-id="b571f-597">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="b571f-598">Os termos são mapeados para o Dayforce como valores de indicador de emprego.</span><span class="sxs-lookup"><span data-stu-id="b571f-598">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="b571f-599">Os termos de emprego e as descrições a seguir são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="b571f-599">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="b571f-600">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="b571f-600">Terms of employment</span></span>   | <span data-ttu-id="b571f-601">descrição</span><span class="sxs-lookup"><span data-stu-id="b571f-601">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="b571f-602">Normal</span><span class="sxs-lookup"><span data-stu-id="b571f-602">Regular</span></span>               | <span data-ttu-id="b571f-603">Normal</span><span class="sxs-lookup"><span data-stu-id="b571f-603">Regular</span></span>     |
| <span data-ttu-id="b571f-604">Direto</span><span class="sxs-lookup"><span data-stu-id="b571f-604">Direct</span></span>                | <span data-ttu-id="b571f-605">Direto</span><span class="sxs-lookup"><span data-stu-id="b571f-605">Direct</span></span>      |
| <span data-ttu-id="b571f-606">Estágio</span><span class="sxs-lookup"><span data-stu-id="b571f-606">Internship</span></span>            | <span data-ttu-id="b571f-607">Estágio</span><span class="sxs-lookup"><span data-stu-id="b571f-607">Internship</span></span>  |
| <span data-ttu-id="b571f-608">Permanente</span><span class="sxs-lookup"><span data-stu-id="b571f-608">Permanent</span></span>             | <span data-ttu-id="b571f-609">Permanente</span><span class="sxs-lookup"><span data-stu-id="b571f-609">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="b571f-610">Estado civil</span><span class="sxs-lookup"><span data-stu-id="b571f-610">Marital status</span></span>

<span data-ttu-id="b571f-611">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-611">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b571f-612">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-612">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="b571f-613">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-613">Talent</span></span>                 | <span data-ttu-id="b571f-614">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-614">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="b571f-615">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-615">Married</span></span>                | <span data-ttu-id="b571f-616">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-616">Married</span></span>                   |
| <span data-ttu-id="b571f-617">Única</span><span class="sxs-lookup"><span data-stu-id="b571f-617">Single</span></span>                 | <span data-ttu-id="b571f-618">Única</span><span class="sxs-lookup"><span data-stu-id="b571f-618">Single</span></span>                    |
| <span data-ttu-id="b571f-619">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-619">Widowed</span></span>                | <span data-ttu-id="b571f-620">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-620">Widowed</span></span>                   |
| <span data-ttu-id="b571f-621">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-621">Divorced</span></span>               | <span data-ttu-id="b571f-622">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-622">Divorced</span></span>                  |
| <span data-ttu-id="b571f-623">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="b571f-623">Registered Partnership</span></span> | <span data-ttu-id="b571f-624">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="b571f-624">Domestic Partnership</span></span>      |
| <span data-ttu-id="b571f-625">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="b571f-625">None</span></span>                   | <span data-ttu-id="b571f-626">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="b571f-626">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b571f-627">Coabitando</span><span class="sxs-lookup"><span data-stu-id="b571f-627">Cohabiting</span></span>             | <span data-ttu-id="b571f-628">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="b571f-628">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="b571f-629">Sexo</span><span class="sxs-lookup"><span data-stu-id="b571f-629">Gender</span></span>

<span data-ttu-id="b571f-630">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-630">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b571f-631">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-631">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="b571f-632">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-632">Talent</span></span>       | <span data-ttu-id="b571f-633">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-633">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="b571f-634">Masculino</span><span class="sxs-lookup"><span data-stu-id="b571f-634">Male</span></span>         | <span data-ttu-id="b571f-635">Masculino</span><span class="sxs-lookup"><span data-stu-id="b571f-635">Male</span></span>                      |
| <span data-ttu-id="b571f-636">Feminino</span><span class="sxs-lookup"><span data-stu-id="b571f-636">Female</span></span>       | <span data-ttu-id="b571f-637">Feminino</span><span class="sxs-lookup"><span data-stu-id="b571f-637">Female</span></span>                    |
| <span data-ttu-id="b571f-638">Não específico</span><span class="sxs-lookup"><span data-stu-id="b571f-638">Non-specific</span></span> | <span data-ttu-id="b571f-639">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="b571f-639">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="b571f-640">Forma de pagamento</span><span class="sxs-lookup"><span data-stu-id="b571f-640">Payment method</span></span>

<span data-ttu-id="b571f-641">Os métodos de pagamento dão ao funcionário e à empresa uma maneira de descrever como os funcionários serão pagos.</span><span class="sxs-lookup"><span data-stu-id="b571f-641">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="b571f-642">Os métodos de pagamento são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-642">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="b571f-643">A tabela a seguir mostra como os métodos de pagamento são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-643">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="b571f-644">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-644">Talent</span></span>             | <span data-ttu-id="b571f-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-645">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="b571f-646">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="b571f-646">Cash</span></span>               | <span data-ttu-id="b571f-647">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="b571f-647">Cash</span></span>                      |
| <span data-ttu-id="b571f-648">Pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="b571f-648">Electronic Payment</span></span> | <span data-ttu-id="b571f-649">Transferência</span><span class="sxs-lookup"><span data-stu-id="b571f-649">Transfer</span></span>                  |
| <span data-ttu-id="b571f-650">Verificação</span><span class="sxs-lookup"><span data-stu-id="b571f-650">Check</span></span>              | <span data-ttu-id="b571f-651">Cheque</span><span class="sxs-lookup"><span data-stu-id="b571f-651">Cheque</span></span>                    |
| <span data-ttu-id="b571f-652">Boleto bancário</span><span class="sxs-lookup"><span data-stu-id="b571f-652">Bank Draft</span></span>         | <span data-ttu-id="b571f-653">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="b571f-653">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b571f-654">Outros</span><span class="sxs-lookup"><span data-stu-id="b571f-654">Other</span></span>              | <span data-ttu-id="b571f-655">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="b571f-655">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="b571f-656">Tipo de conta bancária</span><span class="sxs-lookup"><span data-stu-id="b571f-656">Bank account type</span></span>

<span data-ttu-id="b571f-657">Os tipos de conta bancária são usados para pagamentos eletrônicos aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="b571f-657">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="b571f-658">Os tipos de conta bancária são mapeados para o Dayforce como informações da conta de transferência.</span><span class="sxs-lookup"><span data-stu-id="b571f-658">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="b571f-659">Os tipos de conta bancária são convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="b571f-659">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="b571f-660">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-660">Talent</span></span>            | <span data-ttu-id="b571f-661">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-661">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="b571f-662">Conta corrente</span><span class="sxs-lookup"><span data-stu-id="b571f-662">Checking Account</span></span>  | <span data-ttu-id="b571f-663">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="b571f-663">CheckingAccount</span></span>           |
| <span data-ttu-id="b571f-664">Conta-salário</span><span class="sxs-lookup"><span data-stu-id="b571f-664">Payroll Account</span></span>   | <span data-ttu-id="b571f-665">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="b571f-665">PayrollAccount</span></span>            |
| <span data-ttu-id="b571f-666">Conta de poupança</span><span class="sxs-lookup"><span data-stu-id="b571f-666">Savings Account</span></span>   | <span data-ttu-id="b571f-667">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="b571f-667">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b571f-668">Conta BankGirot</span><span class="sxs-lookup"><span data-stu-id="b571f-668">BankGirot account</span></span> | <span data-ttu-id="b571f-669">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="b571f-669">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="b571f-670">Conta PlusGirot</span><span class="sxs-lookup"><span data-stu-id="b571f-670">PlusGirot account</span></span> | <span data-ttu-id="b571f-671">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="b571f-671">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="b571f-672">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="b571f-672">Earning codes</span></span>

<span data-ttu-id="b571f-673">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="b571f-673">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="b571f-674">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="b571f-674">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="b571f-675">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="b571f-675">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="b571f-676">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="b571f-676">Supported frequencies</span></span>

- <span data-ttu-id="b571f-677">Todas</span><span class="sxs-lookup"><span data-stu-id="b571f-677">All</span></span>
- <span data-ttu-id="b571f-678">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="b571f-678">EVERYPAY</span></span>
- <span data-ttu-id="b571f-679">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="b571f-679">EACHPAYPERIOD</span></span>
- <span data-ttu-id="b571f-680">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="b571f-680">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="b571f-681">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="b571f-681">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="b571f-682">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-682">1OFMTH</span></span>
- <span data-ttu-id="b571f-683">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-683">LASTOFMTH</span></span>
- <span data-ttu-id="b571f-684">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-684">2OFMTH</span></span>
- <span data-ttu-id="b571f-685">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-685">3OFMTH</span></span>
- <span data-ttu-id="b571f-686">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-686">4OFMTH</span></span>
- <span data-ttu-id="b571f-687">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-687">5OFMTH</span></span>
- <span data-ttu-id="b571f-688">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-688">1N2OFMTH</span></span>
- <span data-ttu-id="b571f-689">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-689">3N4OFMTH</span></span>
- <span data-ttu-id="b571f-690">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-690">1N3OFMTH</span></span>
- <span data-ttu-id="b571f-691">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-691">1N4OFMTH</span></span>
- <span data-ttu-id="b571f-692">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-692">2N3OFMTH</span></span>
- <span data-ttu-id="b571f-693">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-693">2N4OFMTH</span></span>
- <span data-ttu-id="b571f-694">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-694">1N2N3OFMTH</span></span>
- <span data-ttu-id="b571f-695">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-695">1N2N4OFMTH</span></span>
- <span data-ttu-id="b571f-696">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-696">1N3N4OFMTH</span></span>
- <span data-ttu-id="b571f-697">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-697">2N3N4OFMTH</span></span>
- <span data-ttu-id="b571f-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="b571f-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="b571f-699">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="b571f-699">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="b571f-700">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="b571f-700">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="b571f-701">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="b571f-701">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="b571f-702">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="b571f-702">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="b571f-703">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="b571f-703">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="b571f-704">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b571f-704">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="b571f-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b571f-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="b571f-706">Endereços</span><span class="sxs-lookup"><span data-stu-id="b571f-706">Addresses</span></span>

<span data-ttu-id="b571f-707">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="b571f-707">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="b571f-708">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="b571f-708">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="b571f-709">Talent</span><span class="sxs-lookup"><span data-stu-id="b571f-709">Talent</span></span>              | <span data-ttu-id="b571f-710">Dayforce</span><span class="sxs-lookup"><span data-stu-id="b571f-710">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="b571f-711">País/Região</span><span class="sxs-lookup"><span data-stu-id="b571f-711">Country/Region</span></span>      | <span data-ttu-id="b571f-712">Código do País</span><span class="sxs-lookup"><span data-stu-id="b571f-712">Country Code</span></span>          |
| <span data-ttu-id="b571f-713">CEP</span><span class="sxs-lookup"><span data-stu-id="b571f-713">Zip/Postal Code</span></span>     | <span data-ttu-id="b571f-714">CEP</span><span class="sxs-lookup"><span data-stu-id="b571f-714">Postal Code</span></span>           |
| <span data-ttu-id="b571f-715">Estadual</span><span class="sxs-lookup"><span data-stu-id="b571f-715">State</span></span>               | <span data-ttu-id="b571f-716">Código de estado</span><span class="sxs-lookup"><span data-stu-id="b571f-716">State Code</span></span>            |
| <span data-ttu-id="b571f-717">Cidade</span><span class="sxs-lookup"><span data-stu-id="b571f-717">City</span></span>                | <span data-ttu-id="b571f-718">Cidade</span><span class="sxs-lookup"><span data-stu-id="b571f-718">City</span></span>                  |
| <span data-ttu-id="b571f-719">Região</span><span class="sxs-lookup"><span data-stu-id="b571f-719">County</span></span>              | <span data-ttu-id="b571f-720">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="b571f-720">County (Municipality)</span></span> |
| <span data-ttu-id="b571f-721">Rua</span><span class="sxs-lookup"><span data-stu-id="b571f-721">Street</span></span>              | <span data-ttu-id="b571f-722">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="b571f-722">Address Line 1</span></span>        |
| <span data-ttu-id="b571f-723">Número</span><span class="sxs-lookup"><span data-stu-id="b571f-723">Street Number</span></span>       | <span data-ttu-id="b571f-724">Linha de endereço 2</span><span class="sxs-lookup"><span data-stu-id="b571f-724">Address Line 2</span></span>        |
| <span data-ttu-id="b571f-725">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="b571f-725">Building Complement</span></span> | <span data-ttu-id="b571f-726">Linha de endereço 5</span><span class="sxs-lookup"><span data-stu-id="b571f-726">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="b571f-727">Número do passaporte</span><span class="sxs-lookup"><span data-stu-id="b571f-727">Passport number</span></span>

<span data-ttu-id="b571f-728">Os funcionários podem declarar as informações do passaporte.</span><span class="sxs-lookup"><span data-stu-id="b571f-728">Employees can declare passport information.</span></span> <span data-ttu-id="b571f-729">Essas informações são do tipo de identificação **Passaporte** e estão integradas ao Dayforce como parte das informações específicas do México de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="b571f-729">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="b571f-730">Tipo de identificação = "Passaporte"</span><span class="sxs-lookup"><span data-stu-id="b571f-730">Identification Type = "Passport"</span></span>
- <span data-ttu-id="b571f-731">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="b571f-731">Issued Date</span></span>
- <span data-ttu-id="b571f-732">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="b571f-732">Expiration Date</span></span>

<span data-ttu-id="b571f-733">Os funcionários podem declarar vários números de identificação do tipo de identificação **Passaporte**.</span><span class="sxs-lookup"><span data-stu-id="b571f-733">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="b571f-734">No entanto, apenas a entrada atual do passaporte ativo é integrada ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-734">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="b571f-735">Se todas as entradas do passaporte expirarem, o passaporte emitido mais recentemente será integrado ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="b571f-735">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
