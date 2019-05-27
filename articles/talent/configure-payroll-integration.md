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
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517292"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="c8a4a-103">Configurar a integração da folha de pagamento entre o Talent e o Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c8a4a-104">A integração entre o Microsoft Dynamics 365 for Talent e o Ceridian Dayforce depende de várias etapas de configuração descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="c8a4a-105">Você deve configurar a integração no Talent e no Dayforce antes de poder processar uma execução de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="c8a4a-106">Ao usar um serviço como o Dayforce para concluir execuções de pagamento, é necessário ativar a integração no Talent.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="c8a4a-107">A integração requer dados específicos do Talent.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="c8a4a-108">Portanto, você deve verificar se os dados mapeados para o Dayforce estão configurados no Talent de forma compatível com a integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="c8a4a-109">A integração usa as seguintes categorias amplas de dados:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="c8a4a-110">Dados de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-110">Human resources data</span></span>
- <span data-ttu-id="c8a4a-111">Dados de remuneração</span><span class="sxs-lookup"><span data-stu-id="c8a4a-111">Compensation data</span></span>
- <span data-ttu-id="c8a4a-112">Dados da folha de pagamento, como ciclos de pagamento, períodos de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="c8a4a-113">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-113">Worker data</span></span>

<span data-ttu-id="c8a4a-114">Este tópico descreve as etapas que você deve seguir para ativar a integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="c8a4a-115">Também explica os tipos de dados e os detalhes de configuração que a integração requer.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="c8a4a-116">Habilitar a integração</span><span class="sxs-lookup"><span data-stu-id="c8a4a-116">Enable the integration</span></span>

<span data-ttu-id="c8a4a-117">No Talent, você deve ativar a integração e inserir as informações de configuração para se conectar ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="c8a4a-118">Para que a transação da contabilidade que for produzida seja importada para o Microsoft Dynamics 365 for Finance and Operations, também é preciso configurar uma conta de armazenamento do Microsoft Azure e inserir a cadeia de conexão do Armazenamento do Azure no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="c8a4a-119">Para ativar a integração no Talent, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="c8a4a-120">Na página **Administração do sistema**, selecione **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="c8a4a-121">Digite o ponto de extremidade seguro do File Transfer Protocol (FTP) e o caminho seguro da pasta FTP.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="c8a4a-122">Digite o nome e a senha do usuário que acessará o ponto de extremidade e o caminho da pasta seguros do FTP.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="c8a4a-123">Teste a conexão, conforme necessário, e defina a opção **Habilitar integração da folha de pagamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="c8a4a-124">Quando a integração é ativada, o pacote e os arquivos de exportação de dados são criados e a frequência é configurada.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="c8a4a-125">Você pode alterar essa frequência conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="c8a4a-126">Para obter mais informações sobre as contas de armazenamento do Azure e as cadeias de conexão do Armazenamento do Azure, consulte os seguintes tópicos do Azure:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="c8a4a-127">Sobre as contas de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="c8a4a-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="c8a4a-128">Configurar cadeias de conexão do Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="c8a4a-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a><span data-ttu-id="c8a4a-129">Configurar seus dados</span><span class="sxs-lookup"><span data-stu-id="c8a4a-129">Configure your data</span></span> 

<span data-ttu-id="c8a4a-130">Para processar a folha de pagamento, você deve configurar dados de RH no Talent.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-130">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="c8a4a-131">Você deve configurar dados organizacionais, como cargos e posições, juntamente com informações sobre benefícios e remuneração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-131">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="c8a4a-132">Esses dados fornecem as informações de emprego, pagamento e dedução necessárias para gerar o pagamento do empregado.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-132">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="c8a4a-133">Dados de RH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-133">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="c8a4a-134">Benefícios</span><span class="sxs-lookup"><span data-stu-id="c8a4a-134">Benefits</span></span> 

<span data-ttu-id="c8a4a-135">O RH fornece ferramentas para a configuração e manutenção dos benefícios, deduções e planos de remuneração do trabalhador que uma organização oferece ou processa para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-135">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="c8a4a-136">Ao criar benefícios, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-136">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="c8a4a-137">Planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="c8a4a-137">Benefit plans</span></span>

- <span data-ttu-id="c8a4a-138">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-138">Plan (required)</span></span>
- <span data-ttu-id="c8a4a-139">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-139">Type (required)</span></span>
- <span data-ttu-id="c8a4a-140">Impacto da folha de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-140">Payroll impact (required)</span></span>
- <span data-ttu-id="c8a4a-141">Recuperar atrasos de pagamento</span><span class="sxs-lookup"><span data-stu-id="c8a4a-141">Recover arrears</span></span>
- <span data-ttu-id="c8a4a-142">Método de dedução</span><span class="sxs-lookup"><span data-stu-id="c8a4a-142">Deduction method</span></span>
- <span data-ttu-id="c8a4a-143">Prioridade da dedução</span><span class="sxs-lookup"><span data-stu-id="c8a4a-143">Deduction priority</span></span>
- <span data-ttu-id="c8a4a-144">Limitar período</span><span class="sxs-lookup"><span data-stu-id="c8a4a-144">Limit period</span></span>
- <span data-ttu-id="c8a4a-145">Valor de limite</span><span class="sxs-lookup"><span data-stu-id="c8a4a-145">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="c8a4a-146">Benefícios</span><span class="sxs-lookup"><span data-stu-id="c8a4a-146">Benefits</span></span>

- <span data-ttu-id="c8a4a-147">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-147">Plan (required)</span></span>
- <span data-ttu-id="c8a4a-148">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-148">Type (required)</span></span>
- <span data-ttu-id="c8a4a-149">Opção (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-149">Option (required)</span></span>
- <span data-ttu-id="c8a4a-150">ID do benefício (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-150">Benefit ID (required)</span></span>
- <span data-ttu-id="c8a4a-151">Frequência</span><span class="sxs-lookup"><span data-stu-id="c8a4a-151">Frequency</span></span>
- <span data-ttu-id="c8a4a-152">Base</span><span class="sxs-lookup"><span data-stu-id="c8a4a-152">Basis</span></span>
- <span data-ttu-id="c8a4a-153">Valor ou taxa</span><span class="sxs-lookup"><span data-stu-id="c8a4a-153">Amount or rate</span></span>
- <span data-ttu-id="c8a4a-154">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-154">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="c8a4a-155">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="c8a4a-155">Supported frequencies</span></span> 

- <span data-ttu-id="c8a4a-156">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="c8a4a-156">Weekly</span></span>
- <span data-ttu-id="c8a4a-157">Por quinzena</span><span class="sxs-lookup"><span data-stu-id="c8a4a-157">Bi-weekly</span></span>
- <span data-ttu-id="c8a4a-158">Quinzenal</span><span class="sxs-lookup"><span data-stu-id="c8a4a-158">Semi-monthly</span></span>
- <span data-ttu-id="c8a4a-159">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="c8a4a-159">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="c8a4a-160">Bases com suporte</span><span class="sxs-lookup"><span data-stu-id="c8a4a-160">Supported bases</span></span> 

- <span data-ttu-id="c8a4a-161">Valor fixo</span><span class="sxs-lookup"><span data-stu-id="c8a4a-161">Fixed amount</span></span>
- <span data-ttu-id="c8a4a-162">Percentual de ganhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-162">Percent of earnings</span></span>
- <span data-ttu-id="c8a4a-163">Horas produtivas</span><span class="sxs-lookup"><span data-stu-id="c8a4a-163">Productive hours</span></span>

<span data-ttu-id="c8a4a-164">O Dayforce cria as deduções a seguir, com base no impacto da folha de pagamento definido no plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-164">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="c8a4a-165">Seleção no Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-165">Selection in Talent</span></span>        | <span data-ttu-id="c8a4a-166">Resultado no Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-166">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="c8a4a-167">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-167">None</span></span>                       | <span data-ttu-id="c8a4a-168">Nenhuma dedução é criada.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-168">No deduction is created.</span></span>                      |
| <span data-ttu-id="c8a4a-169">Somente dedução</span><span class="sxs-lookup"><span data-stu-id="c8a4a-169">Deduction only</span></span>             | <span data-ttu-id="c8a4a-170">Uma dedução de funcionário é criada.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-170">An employee deduction is created.</span></span>             |
| <span data-ttu-id="c8a4a-171">Somente contribuição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-171">Contribution only</span></span>          | <span data-ttu-id="c8a4a-172">Uma dedução de empregador é criada.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-172">An employer deduction is created.</span></span>             |
| <span data-ttu-id="c8a4a-173">Dedução e contribuição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-173">Deduction and contribution</span></span> | <span data-ttu-id="c8a4a-174">Deduções de funcionário e empregador são criadas.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-174">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="c8a4a-175">Para obter mais informações sobre como definir e gerenciar um programa de benefícios, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-175">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="c8a4a-176">Entregar um programa de benefícios do funcionário</span><span class="sxs-lookup"><span data-stu-id="c8a4a-176">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="c8a4a-177">Criar um novo benefício</span><span class="sxs-lookup"><span data-stu-id="c8a4a-177">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="c8a4a-178">Definir regras e políticas de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="c8a4a-178">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="c8a4a-179">Inscrever e remover benefícios de trabalhadores</span><span class="sxs-lookup"><span data-stu-id="c8a4a-179">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="c8a4a-180">Remuneração</span><span class="sxs-lookup"><span data-stu-id="c8a4a-180">Compensation</span></span> 

<span data-ttu-id="c8a4a-181">O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-181">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="c8a4a-182">Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-182">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="c8a4a-183">O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-183">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="c8a4a-184">O Dayforce usa informações de remuneração para calcular a taxa por hora ou anual de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-184">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="c8a4a-185">Planos de remuneração fixa e conversões de taxa de pagamento são necessários.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-185">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="c8a4a-186">Os funcionários devem estar associados a um plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-186">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="c8a4a-187">Para obter mais informações sobre planos de remuneração, veja os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-187">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="c8a4a-188">Criar planos de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="c8a4a-188">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="c8a4a-189">Criar planos de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="c8a4a-189">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="c8a4a-190">Desenvolver estrutura e planos de remuneração/salário</span><span class="sxs-lookup"><span data-stu-id="c8a4a-190">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="c8a4a-191">Processar remuneração</span><span class="sxs-lookup"><span data-stu-id="c8a4a-191">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="c8a4a-192">Definir processo de remuneração e calcular resultados</span><span class="sxs-lookup"><span data-stu-id="c8a4a-192">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="c8a4a-193">Inscrever um funcionário em um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="c8a4a-193">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="c8a4a-194">Inscrever um funcionário em um plano de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="c8a4a-194">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="c8a4a-195">Trabalhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-195">Jobs</span></span> 

<span data-ttu-id="c8a4a-196">Um trabalho é um conjunto de tarefas e responsabilidades exigidas de uma pessoa que realiza um trabalho.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-196">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="c8a4a-197">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-197">For more information, see the following topics:</span></span>

- [<span data-ttu-id="c8a4a-198">Configurando os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="c8a4a-198">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="c8a4a-199">Definir novos trabalhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-199">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="c8a4a-200">Posições</span><span class="sxs-lookup"><span data-stu-id="c8a4a-200">Positions</span></span>

<span data-ttu-id="c8a4a-201">Um cargo é uma instância individual de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-201">A position is an individual instance of a job.</span></span> <span data-ttu-id="c8a4a-202">Por exemplo, a posição "Gerente de vendas (Leste)" é uma das posições associadas ao trabalho "Gerente de vendas".</span><span class="sxs-lookup"><span data-stu-id="c8a4a-202">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="c8a4a-203">Uma posição existe em um departamento.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-203">A position exists in a department.</span></span> <span data-ttu-id="c8a4a-204">Apenas um trabalhador pode ser associado a cada posição.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-204">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="c8a4a-205">Considere os seguintes dados e configurações ao configurar as posições:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-205">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="c8a4a-206">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-206">Position (required)</span></span>
- <span data-ttu-id="c8a4a-207">Descrição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-207">Description (required)</span></span>
- <span data-ttu-id="c8a4a-208">Trabalho (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-208">Job (required)</span></span>
- <span data-ttu-id="c8a4a-209">Departamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-209">Department (required)</span></span>
- <span data-ttu-id="c8a4a-210">Tipo de posição (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-210">Position type (required)</span></span>
- <span data-ttu-id="c8a4a-211">Equivalente ao horário integral</span><span class="sxs-lookup"><span data-stu-id="c8a4a-211">Full-time equivalent</span></span>
- <span data-ttu-id="c8a4a-212">Horas normais anuais (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-212">Annual regular hours (required)</span></span>
- <span data-ttu-id="c8a4a-213">Pago por entidade legal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-213">Paid by legal entity (required)</span></span>
- <span data-ttu-id="c8a4a-214">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-214">Pay cycle (required)</span></span>
- <span data-ttu-id="c8a4a-215">Dimensão financeira padrão – Centro de custo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-215">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="c8a4a-216">Atribuição do trabalhador – Trabalhador, início da atribuição, fim da atribuição, código de motivo</span><span class="sxs-lookup"><span data-stu-id="c8a4a-216">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="c8a4a-217">Se várias posições no mesmo departamento estiverem associadas ao mesmo trabalho, elas serão consolidadas em uma única posição no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-217">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="c8a4a-218">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-218">For more information, see the following topics:</span></span>

- [<span data-ttu-id="c8a4a-219">Organizar sua força de trabalho usando departamentos, trabalhos e posições</span><span class="sxs-lookup"><span data-stu-id="c8a4a-219">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="c8a4a-220">Configurar posições</span><span class="sxs-lookup"><span data-stu-id="c8a4a-220">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="c8a4a-221">Departamentos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-221">Departments</span></span>

<span data-ttu-id="c8a4a-222">Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-222">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="c8a4a-223">Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-223">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="c8a4a-224">Você pode usar departamentos para relatar áreas funcionais.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-224">You can use departments to report on functional areas.</span></span> <span data-ttu-id="c8a4a-225">Os departamentos podem ter a responsabilidade de lucros e perdas.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-225">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="c8a4a-226">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-226">For more information, see the following topics:</span></span>

- [<span data-ttu-id="c8a4a-227">Criar um departamento e associá-lo à hierarquia de departamentos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-227">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="c8a4a-228">Definir novos departamentos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-228">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="c8a4a-229">Ciclos de pagamento e períodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="c8a4a-229">Pay cycles and pay periods</span></span>

<span data-ttu-id="c8a4a-230">Um ciclo de pagamento determina a frequência com que a folha de pagamento é executada e os dias específicos em que os trabalhadores são pagos.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-230">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="c8a4a-231">Por exemplo, um ciclo de pagamento pode ser mensal e os funcionários podem ser pagos no último dia do mês.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-231">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="c8a4a-232">Como alternativa, um ciclo de pagamento pode ser semanal e os funcionários podem ser pagos na terça-feira após o término do período de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-232">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="c8a4a-233">Ciclos de pagamento são atribuídos a posições para controlar quando os trabalhadores nessas posições são pagos.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-233">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="c8a4a-234">Após a criação dos ciclos de pagamento, você pode gerar períodos de pagamento para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-234">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="c8a4a-235">Cada período de pagamento inclui uma data de pagamento padrão baseada nas informações que você fornece.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-235">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="c8a4a-236">No entanto, você pode modificar a data de pagamento padrão em um período de pagamento para permitir exceções (por exemplo, quando a data de pagamento cai em um feriado).</span><span class="sxs-lookup"><span data-stu-id="c8a4a-236">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="c8a4a-237">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-237">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="c8a4a-238">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-238">Pay cycle (required)</span></span>
- <span data-ttu-id="c8a4a-239">Frequência do ciclo de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-239">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="c8a4a-240">Data de início do período (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-240">Period start date (first pay period required)</span></span>
- <span data-ttu-id="c8a4a-241">Data de pagamento padrão (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-241">Default payment date (first pay period required)</span></span>

<span data-ttu-id="c8a4a-242">Essas informações são integradas ao Dayforce como grupos de pagamento e são separadas por país ou região para cada ciclo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-242">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="c8a4a-243">Pelo menos um período de pagamento deve ser gerado antes da integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-243">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="c8a4a-244">O Dayforce gera datas de pagamento e calendários do grupo de pagamento, com base na data de início do primeiro período de pagamento e na data de pagamento padrão configurada no Talent.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-244">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="c8a4a-245">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-245">Earning codes</span></span>

<span data-ttu-id="c8a4a-246">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-246">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="c8a4a-247">Os códigos têm vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-247">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="c8a4a-248">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="c8a4a-249">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-249">Earning Code (required)</span></span>
- <span data-ttu-id="c8a4a-250">descrição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-250">Description</span></span>
- <span data-ttu-id="c8a4a-251">Unidade de medida</span><span class="sxs-lookup"><span data-stu-id="c8a4a-251">Unit of measure</span></span>
- <span data-ttu-id="c8a4a-252">Produtivo</span><span class="sxs-lookup"><span data-stu-id="c8a4a-252">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="c8a4a-253">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-253">Worker data</span></span>

<span data-ttu-id="c8a4a-254">Os registros dos vários tipos de trabalhadores que você tem são importantes para o RH e sistemas de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-254">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="c8a4a-255">As informações inseridas podem ser usadas para rastrear trabalhadores e informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-255">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="c8a4a-256">Você pode manter estas informações para trabalhadores:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-256">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="c8a4a-257">**Básicas** – mantenha informações básicas do trabalhador, como informações de contato, demográficas, de identificação, sobre a família, o status de serviço militar, informações de exilado, contatos pessoais e de emergência.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-257">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="c8a4a-258">**Emprego** – mantenha informações sobre o emprego dos trabalhadores, como a afiliação da empresa ou organização, a atribuição de posição, as datas inicial e final, a qualificação para trabalho, o contrato de trabalho, a pensão, férias e as informações de mudança.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-258">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="c8a4a-259">**Licença e ausência** – mantenha informações sobre as ausências dos trabalhadores, como o calendário de trabalho, as transações de ausência e a configuração de ausência.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-259">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="c8a4a-260">**Remuneração e folha de pagamento** – mantenha informações sobre os planos de remuneração e as informações de folha de pagamento de trabalhadores, como o registro do plano, prêmios, o desempenho, a comissão, informações sobre impostos, aposentadoria e deduções do salário.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-260">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="c8a4a-261">Ao inserir informações do trabalhador, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-261">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="c8a4a-262">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="c8a4a-262">General information</span></span>

- <span data-ttu-id="c8a4a-263">Número de equipe (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-263">Personnel number (required)</span></span>
- <span data-ttu-id="c8a4a-264">Nome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-264">First name (required)</span></span>
- <span data-ttu-id="c8a4a-265">Sobrenome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-265">Last name (required)</span></span>
- <span data-ttu-id="c8a4a-266">Nome do meio</span><span class="sxs-lookup"><span data-stu-id="c8a4a-266">Middle name</span></span>
- <span data-ttu-id="c8a4a-267">Aniversário de tempo de serviço</span><span class="sxs-lookup"><span data-stu-id="c8a4a-267">Seniority date</span></span>
- <span data-ttu-id="c8a4a-268">Conhecido como</span><span class="sxs-lookup"><span data-stu-id="c8a4a-268">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="c8a4a-269">Informações pessoais</span><span class="sxs-lookup"><span data-stu-id="c8a4a-269">Personal information</span></span>

- <span data-ttu-id="c8a4a-270">Estado civil (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-270">Marital status (required)</span></span>
- <span data-ttu-id="c8a4a-271">Data de nascimento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-271">Birth date (required)</span></span>
- <span data-ttu-id="c8a4a-272">Sexo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-272">Gender (required)</span></span>
- <span data-ttu-id="c8a4a-273">Pessoa portadora de deficiências</span><span class="sxs-lookup"><span data-stu-id="c8a4a-273">Person with disabilities</span></span>
- <span data-ttu-id="c8a4a-274">Região do país de nacionalidade (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-274">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="c8a4a-275">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="c8a4a-275">Address information</span></span>

- <span data-ttu-id="c8a4a-276">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-276">Primary (required)</span></span>
- <span data-ttu-id="c8a4a-277">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-277">Country/region (required)</span></span>
- <span data-ttu-id="c8a4a-278">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-278">Postal code (required)</span></span>
- <span data-ttu-id="c8a4a-279">Número da rua (obrigatório) (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-279">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="c8a4a-280">Complemento do edifício (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-280">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="c8a4a-281">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-281">City (required)</span></span>
- <span data-ttu-id="c8a4a-282">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-282">State (required)</span></span>
- <span data-ttu-id="c8a4a-283">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-283">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="c8a4a-284">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="c8a4a-284">Contact information</span></span> 

- <span data-ttu-id="c8a4a-285">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-285">Primary (required)</span></span>
- <span data-ttu-id="c8a4a-286">Número de contato (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-286">Contact number (required)</span></span>
- <span data-ttu-id="c8a4a-287">Extensão</span><span class="sxs-lookup"><span data-stu-id="c8a4a-287">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="c8a4a-288">Informações sobre folha de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-288">Payroll information and earning codes</span></span>

<span data-ttu-id="c8a4a-289">Os funcionários podem receber ganhos específicos com uma determinada frequência de pagamento e ter um método de pagamento preferencial.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-289">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="c8a4a-290">Os campos a seguir são usados no Dayforce para ajudar a garantir que essas preferências e configurações sejam usadas.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-290">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="c8a4a-291">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-291">Earning codes</span></span>

- <span data-ttu-id="c8a4a-292">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-292">Position (required)</span></span>
- <span data-ttu-id="c8a4a-293">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-293">Earning Code (required)</span></span>
- <span data-ttu-id="c8a4a-294">Frequência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-294">Frequency (required)</span></span>
- <span data-ttu-id="c8a4a-295">Valor (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-295">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="c8a4a-296">Informações da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="c8a4a-296">Payroll information</span></span>

- <span data-ttu-id="c8a4a-297">Método de Pagamento</span><span class="sxs-lookup"><span data-stu-id="c8a4a-297">Payment Method</span></span>
- <span data-ttu-id="c8a4a-298">Região econômica (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-298">Economic Region (required)</span></span>
- <span data-ttu-id="c8a4a-299">ID de Benefícios do Funcionário</span><span class="sxs-lookup"><span data-stu-id="c8a4a-299">Employee Benefits ID</span></span>
- <span data-ttu-id="c8a4a-300">Número de ID nacional (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-300">National ID Number (required)</span></span>
- <span data-ttu-id="c8a4a-301">Número de serviço militar</span><span class="sxs-lookup"><span data-stu-id="c8a4a-301">Military Service Number</span></span>
- <span data-ttu-id="c8a4a-302">ID de turno (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-302">Shift ID (required)</span></span>
- <span data-ttu-id="c8a4a-303">Número fiscal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-303">Tax Number (required)</span></span>
- <span data-ttu-id="c8a4a-304">ID do sindicato (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-304">Union ID (required)</span></span>
- <span data-ttu-id="c8a4a-305">ID do dia útil (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-305">Work Day ID (required)</span></span>
- <span data-ttu-id="c8a4a-306">Número de autorização de trabalho</span><span class="sxs-lookup"><span data-stu-id="c8a4a-306">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="c8a4a-307">Para o método de pagamento, o México permite **Pagamento à vista**, **Cheque** (o cheque físico da empresa) e **Pagamento Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-307">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="c8a4a-308">Se nenhum método de pagamento for especificado, **Cheque** é usado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-308">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="c8a4a-309">Detalhes do emprego</span><span class="sxs-lookup"><span data-stu-id="c8a4a-309">Employment details</span></span>

<span data-ttu-id="c8a4a-310">O histórico de detalhes de emprego é usado como principal informação para derivar os status de contratação, rescisão e recontratação de um funcionário no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-310">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="c8a4a-311">O Dayforce suporta apenas um registro de emprego ativo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-311">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="c8a4a-312">Data de início do emprego (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-312">Employment start date (required)</span></span>
- <span data-ttu-id="c8a4a-313">Data final do emprego</span><span class="sxs-lookup"><span data-stu-id="c8a4a-313">Employment end date</span></span>
- <span data-ttu-id="c8a4a-314">Data de início</span><span class="sxs-lookup"><span data-stu-id="c8a4a-314">Start date</span></span>
- <span data-ttu-id="c8a4a-315">Data inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="c8a4a-315">Adjusted start date</span></span>
- <span data-ttu-id="c8a4a-316">Data de rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-316">Termination date (required upon termination)</span></span>
- <span data-ttu-id="c8a4a-317">Motivo da rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-317">Termination reason (required upon termination)</span></span>

<span data-ttu-id="c8a4a-318">As principais datas de um funcionário são derivadas usando-se as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-318">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="c8a4a-319">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-319">Talent</span></span>                | <span data-ttu-id="c8a4a-320">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-320">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c8a4a-321">Data de contratação mais recente</span><span class="sxs-lookup"><span data-stu-id="c8a4a-321">Most recent hire date</span></span> | <span data-ttu-id="c8a4a-322">Início de emprego do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="c8a4a-322">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="c8a4a-323">Data da rescisão</span><span class="sxs-lookup"><span data-stu-id="c8a4a-323">Termination date</span></span>      | <span data-ttu-id="c8a4a-324">Data de rescisão do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="c8a4a-324">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="c8a4a-325">Data de início</span><span class="sxs-lookup"><span data-stu-id="c8a4a-325">Start date</span></span>            | <span data-ttu-id="c8a4a-326">Data de início ajustada, data de início ou início de emprego do registro histórico de emprego não ativo atual</span><span class="sxs-lookup"><span data-stu-id="c8a4a-326">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="c8a4a-327">Data original de contratação</span><span class="sxs-lookup"><span data-stu-id="c8a4a-327">Original hire date</span></span>    | <span data-ttu-id="c8a4a-328">Início de emprego do registro histórico de emprego mais antigo</span><span class="sxs-lookup"><span data-stu-id="c8a4a-328">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="c8a4a-329">Remuneração</span><span class="sxs-lookup"><span data-stu-id="c8a4a-329">Compensation</span></span>

<span data-ttu-id="c8a4a-330">Um plano de remuneração fixa deve estar associado à posição principal de cada funcionário durante um período de emprego.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-330">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="c8a4a-331">Esse período tem início na data em que o funcionário foi contratado (ou na data de início do emprego) e continua até a rescisão.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-331">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="c8a4a-332">Data de vigência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-332">Effective Date (required)</span></span>
- <span data-ttu-id="c8a4a-333">Data de validade</span><span class="sxs-lookup"><span data-stu-id="c8a4a-333">Expiration date</span></span>
- <span data-ttu-id="c8a4a-334">Taxa de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-334">Pay Rate (required)</span></span>
- <span data-ttu-id="c8a4a-335">Conversões de taxa de pagamento (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-335">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="c8a4a-336">Equivalente anual (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-336">Annual equivalent (required)</span></span>
- <span data-ttu-id="c8a4a-337">Equivalente por hora (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-337">Hourly equivalent (required)</span></span>

<span data-ttu-id="c8a4a-338">Se um funcionário por hora tiver várias posições, a remuneração fixa da posição principal é importada para o Dayforce como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-338">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="c8a4a-339">Para posições não principais, a taxa por hora é salva na posição correspondente no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-339">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="c8a4a-340">Se um funcionário assalariado tiver várias posições, a taxa acumulada de horas e o salário anual em todas as posições ativas serão derivados e usados como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-340">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="c8a4a-341">Números de identificação</span><span class="sxs-lookup"><span data-stu-id="c8a4a-341">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="c8a4a-342">Cadastro de Pessoa Física (CPF)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-342">Social Security identifier</span></span> 

<span data-ttu-id="c8a4a-343">Todos os funcionários devem ter um identificador principal.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-343">Every employee must have one primary identifier.</span></span> <span data-ttu-id="c8a4a-344">Esse identificador deve ser o tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-344">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="c8a4a-345">No Dayforce, ele é derivado automaticamente como o identificador de pessoa física do funcionário necessário para a contratação.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-345">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="c8a4a-346">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-346">Primary (required)</span></span>
- <span data-ttu-id="c8a4a-347">Tipo de identificação = "CPF"</span><span class="sxs-lookup"><span data-stu-id="c8a4a-347">Identification Type = "SSN"</span></span>
- <span data-ttu-id="c8a4a-348">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="c8a4a-348">Issued Date</span></span>
- <span data-ttu-id="c8a4a-349">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="c8a4a-349">Expiration Date</span></span>

<span data-ttu-id="c8a4a-350">Os funcionários podem declarar vários números de identificação do tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-350">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="c8a4a-351">No entanto, somente o registro marcado como **Principal** será integrado ao Dayforce, independentemente de o número estar ativo ou expirado.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-351">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="c8a4a-352">Contas bancárias e pagamentos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-352">Bank accounts and disbursements</span></span>

<span data-ttu-id="c8a4a-353">Informações de conta bancária válidas devem ser inseridas para qualquer funcionário que opte por ser pago por meio de transferências bancárias.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-353">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="c8a4a-354">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-354">Talent</span></span>                         | <span data-ttu-id="c8a4a-355">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-355">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c8a4a-356">Número da conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-356">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="c8a4a-357">Código SWIFT (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-357">SWIFT code (required)</span></span>          | <span data-ttu-id="c8a4a-358">Campo **ID do banco** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-358">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="c8a4a-359">Número da agência (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-359">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="c8a4a-360">Tipo de conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-360">Bank account type (required)</span></span>   | <span data-ttu-id="c8a4a-361">Campo **Tipo de conta** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-361">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="c8a4a-362">Os valores com suporte incluem **Movimento** e **Folha de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-362">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="c8a4a-363">Os funcionários que optarem por serem pagos por meio de transferências bancárias deverão fornecer um link para uma conta de pendência em uma entidade legal que tenha seu endereço principal no México e esteja associada a uma conta bancária válida de um banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-363">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="c8a4a-364">Todas as outras contas que não são de pendência são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-364">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="c8a4a-365">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="c8a4a-365">Address information</span></span>

<span data-ttu-id="c8a4a-366">Todos os funcionários devem ter um local principal.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-366">Every employee must have one primary location.</span></span> <span data-ttu-id="c8a4a-367">No Dayforce, esse local é usado para determinar a residência principal do funcionário para fins fiscais.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-367">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="c8a4a-368">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-368">Primary (required)</span></span>
- <span data-ttu-id="c8a4a-369">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-369">Country/region (required)</span></span>
- <span data-ttu-id="c8a4a-370">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-370">Zip/postal code (required)</span></span>
- <span data-ttu-id="c8a4a-371">Rua (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-371">Street (required)</span></span>
- <span data-ttu-id="c8a4a-372">Número da rua (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-372">Street Number (required)</span></span>
- <span data-ttu-id="c8a4a-373">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="c8a4a-373">Building Complement</span></span>
- <span data-ttu-id="c8a4a-374">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-374">City (required)</span></span>
- <span data-ttu-id="c8a4a-375">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-375">State (required)</span></span>
- <span data-ttu-id="c8a4a-376">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-376">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="c8a4a-377">Configurar seus dados para gerar folha de pagamento nos Estados Unidos e no Canadá</span><span class="sxs-lookup"><span data-stu-id="c8a4a-377">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="c8a4a-378">Se você está gerando pagamento para funcionários nos Estados Unidos e no Canadá, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-378">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="c8a4a-379">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-379">Departments are required on positions.</span></span>
- <span data-ttu-id="c8a4a-380">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-380">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="c8a4a-381">Você pode configurar o Talent para exigir que Posições especifique um Departamento.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-381">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="c8a4a-382">Para isso, acesse **Posições Compartilhadas de Recursos Humanos > Posições > Exigir departamentos nas posições**.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-382">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="c8a4a-383">Recomendamos que esta configuração seja imposta para a integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-383">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="c8a4a-384">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="c8a4a-384">Job types</span></span>

<span data-ttu-id="c8a4a-385">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-385">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="c8a4a-386">Os tipos de trabalho são necessários para processar a folha de pagamento nos Estados Unidos e no Canadá.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-386">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="c8a4a-387">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-387">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="c8a4a-388">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-388">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="c8a4a-389">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-389">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="c8a4a-390">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c8a4a-390">Job type</span></span>   | <span data-ttu-id="c8a4a-391">descrição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-391">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="c8a4a-392">Por hora</span><span class="sxs-lookup"><span data-stu-id="c8a4a-392">Hourly</span></span>     | <span data-ttu-id="c8a4a-393">Por hora</span><span class="sxs-lookup"><span data-stu-id="c8a4a-393">Hourly</span></span>      |
| <span data-ttu-id="c8a4a-394">Assalariado</span><span class="sxs-lookup"><span data-stu-id="c8a4a-394">Salaried</span></span>   | <span data-ttu-id="c8a4a-395">Assalariado</span><span class="sxs-lookup"><span data-stu-id="c8a4a-395">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="c8a4a-396">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-396">Position types</span></span> 

<span data-ttu-id="c8a4a-397">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-397">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="c8a4a-398">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-398">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="c8a4a-399">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-399">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="c8a4a-400">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-400">Position type</span></span>   | <span data-ttu-id="c8a4a-401">descrição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-401">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="c8a4a-402">Horário integral</span><span class="sxs-lookup"><span data-stu-id="c8a4a-402">Full-time</span></span>       | <span data-ttu-id="c8a4a-403">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="c8a4a-403">Full time employee</span></span> |
| <span data-ttu-id="c8a4a-404">Meio período</span><span class="sxs-lookup"><span data-stu-id="c8a4a-404">Part-time</span></span>       | <span data-ttu-id="c8a4a-405">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="c8a4a-405">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="c8a4a-406">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-406">Reason codes</span></span>

<span data-ttu-id="c8a4a-407">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-407">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="c8a4a-408">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-408">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="c8a4a-409">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-409">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="c8a4a-410">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="c8a4a-410">Reason code</span></span>    | <span data-ttu-id="c8a4a-411">descrição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-411">Description</span></span>      | <span data-ttu-id="c8a4a-412">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="c8a4a-412">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="c8a4a-413">DEMISSÃO</span><span class="sxs-lookup"><span data-stu-id="c8a4a-413">RESIGNATION</span></span>    | <span data-ttu-id="c8a4a-414">Demissão</span><span class="sxs-lookup"><span data-stu-id="c8a4a-414">Resignation</span></span>      | <span data-ttu-id="c8a4a-415">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-415">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-416">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="c8a4a-416">TERMINATION</span></span>    | <span data-ttu-id="c8a4a-417">Finalização</span><span class="sxs-lookup"><span data-stu-id="c8a4a-417">Termination</span></span>      | <span data-ttu-id="c8a4a-418">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-418">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-419">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="c8a4a-419">RETIREMENT</span></span>     | <span data-ttu-id="c8a4a-420">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="c8a4a-420">Retirement</span></span>       | <span data-ttu-id="c8a4a-421">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-421">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-422">OTHER</span><span class="sxs-lookup"><span data-stu-id="c8a4a-422">OTHER</span></span>          | <span data-ttu-id="c8a4a-423">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-423">Other Reasons</span></span>    | <span data-ttu-id="c8a4a-424">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-424">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-425">DEATH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-425">DEATH</span></span>          | <span data-ttu-id="c8a4a-426">Morte</span><span class="sxs-lookup"><span data-stu-id="c8a4a-426">Death</span></span>            | <span data-ttu-id="c8a4a-427">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-427">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-428">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="c8a4a-428">LEAVEOFABSENCE</span></span> | <span data-ttu-id="c8a4a-429">Licença</span><span class="sxs-lookup"><span data-stu-id="c8a4a-429">Leave of Absence</span></span> | <span data-ttu-id="c8a4a-430">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-430">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-431">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="c8a4a-431">CONTRACTEND</span></span>    | <span data-ttu-id="c8a4a-432">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="c8a4a-432">End of Contract</span></span>  | <span data-ttu-id="c8a4a-433">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-433">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-434">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="c8a4a-434">SALARYCHANGE</span></span>   | <span data-ttu-id="c8a4a-435">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="c8a4a-435">Change of Salary</span></span> | <span data-ttu-id="c8a4a-436">Remuneração</span><span class="sxs-lookup"><span data-stu-id="c8a4a-436">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="c8a4a-437">Estado civil</span><span class="sxs-lookup"><span data-stu-id="c8a4a-437">Marital status</span></span>

<span data-ttu-id="c8a4a-438">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-438">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="c8a4a-439">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-439">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="c8a4a-440">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-440">Talent</span></span>                 | <span data-ttu-id="c8a4a-441">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-441">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="c8a4a-442">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-442">Married</span></span>                | <span data-ttu-id="c8a4a-443">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-443">Married</span></span>              |
| <span data-ttu-id="c8a4a-444">Única</span><span class="sxs-lookup"><span data-stu-id="c8a4a-444">Single</span></span>                 | <span data-ttu-id="c8a4a-445">Única</span><span class="sxs-lookup"><span data-stu-id="c8a4a-445">Single</span></span>               |
| <span data-ttu-id="c8a4a-446">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-446">Widowed</span></span>                | <span data-ttu-id="c8a4a-447">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-447">Widowed</span></span>              |
| <span data-ttu-id="c8a4a-448">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-448">Divorced</span></span>               | <span data-ttu-id="c8a4a-449">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-449">Divorced</span></span>             |
| <span data-ttu-id="c8a4a-450">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="c8a4a-450">Registered Partnership</span></span> | <span data-ttu-id="c8a4a-451">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="c8a4a-451">Domestic Partnership</span></span> |
| <span data-ttu-id="c8a4a-452">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-452">None</span></span>                   | <span data-ttu-id="c8a4a-453">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-453">None</span></span>                 |
| <span data-ttu-id="c8a4a-454">Coabitando</span><span class="sxs-lookup"><span data-stu-id="c8a4a-454">Cohabiting</span></span>             | <span data-ttu-id="c8a4a-455">Coabitando</span><span class="sxs-lookup"><span data-stu-id="c8a4a-455">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="c8a4a-456">Sexo</span><span class="sxs-lookup"><span data-stu-id="c8a4a-456">Gender</span></span>

<span data-ttu-id="c8a4a-457">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-457">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="c8a4a-458">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-458">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="c8a4a-459">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-459">Talent</span></span>       | <span data-ttu-id="c8a4a-460">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-460">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="c8a4a-461">Masculino</span><span class="sxs-lookup"><span data-stu-id="c8a4a-461">Male</span></span>         | <span data-ttu-id="c8a4a-462">Masculino</span><span class="sxs-lookup"><span data-stu-id="c8a4a-462">Male</span></span>            |
| <span data-ttu-id="c8a4a-463">Feminino</span><span class="sxs-lookup"><span data-stu-id="c8a4a-463">Female</span></span>       | <span data-ttu-id="c8a4a-464">Feminino</span><span class="sxs-lookup"><span data-stu-id="c8a4a-464">Female</span></span>          |
| <span data-ttu-id="c8a4a-465">Não específico</span><span class="sxs-lookup"><span data-stu-id="c8a4a-465">Non-specific</span></span> | <span data-ttu-id="c8a4a-466">*Sem suporte*</span><span class="sxs-lookup"><span data-stu-id="c8a4a-466">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="c8a4a-467">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-467">Earning codes</span></span>

<span data-ttu-id="c8a4a-468">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-468">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="c8a4a-469">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-469">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="c8a4a-470">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-470">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="c8a4a-471">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="c8a4a-471">Supported frequencies</span></span>

- <span data-ttu-id="c8a4a-472">Todas</span><span class="sxs-lookup"><span data-stu-id="c8a4a-472">All</span></span>
- <span data-ttu-id="c8a4a-473">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="c8a4a-473">EVERYPAY</span></span>
- <span data-ttu-id="c8a4a-474">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="c8a4a-474">EACHPAYPERIOD</span></span>
- <span data-ttu-id="c8a4a-475">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="c8a4a-475">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="c8a4a-476">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="c8a4a-476">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="c8a4a-477">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-477">1OFMTH</span></span>
- <span data-ttu-id="c8a4a-478">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-478">LASTOFMTH</span></span>
- <span data-ttu-id="c8a4a-479">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-479">2OFMTH</span></span>
- <span data-ttu-id="c8a4a-480">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-480">3OFMTH</span></span>
- <span data-ttu-id="c8a4a-481">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-481">4OFMTH</span></span>
- <span data-ttu-id="c8a4a-482">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-482">5OFMTH</span></span>
- <span data-ttu-id="c8a4a-483">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-483">1N2OFMTH</span></span>
- <span data-ttu-id="c8a4a-484">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-484">3N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-485">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-485">1N3OFMTH</span></span>
- <span data-ttu-id="c8a4a-486">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-486">1N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-487">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-487">2N3OFMTH</span></span>
- <span data-ttu-id="c8a4a-488">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-488">2N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-489">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-489">1N2N3OFMTH</span></span>
- <span data-ttu-id="c8a4a-490">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-490">1N2N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-491">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-491">1N3N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-492">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-492">2N3N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-493">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-494">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="c8a4a-494">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="c8a4a-495">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-495">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="c8a4a-496">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-496">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="c8a4a-497">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-497">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="c8a4a-498">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-498">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="c8a4a-499">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-499">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="c8a4a-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-500">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="c8a4a-501">Endereços</span><span class="sxs-lookup"><span data-stu-id="c8a4a-501">Addresses</span></span>

<span data-ttu-id="c8a4a-502">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-502">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="c8a4a-503">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-503">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="c8a4a-504">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-504">Talent</span></span>          | <span data-ttu-id="c8a4a-505">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-505">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="c8a4a-506">País/Região</span><span class="sxs-lookup"><span data-stu-id="c8a4a-506">Country/Region</span></span>  | <span data-ttu-id="c8a4a-507">Código do País</span><span class="sxs-lookup"><span data-stu-id="c8a4a-507">Country Code</span></span>          |
| <span data-ttu-id="c8a4a-508">CEP</span><span class="sxs-lookup"><span data-stu-id="c8a4a-508">Zip/Postal Code</span></span> | <span data-ttu-id="c8a4a-509">CEP</span><span class="sxs-lookup"><span data-stu-id="c8a4a-509">Postal Code</span></span>           |
| <span data-ttu-id="c8a4a-510">Estadual</span><span class="sxs-lookup"><span data-stu-id="c8a4a-510">State</span></span>           | <span data-ttu-id="c8a4a-511">Código de estado</span><span class="sxs-lookup"><span data-stu-id="c8a4a-511">State Code</span></span>            |
| <span data-ttu-id="c8a4a-512">Cidade</span><span class="sxs-lookup"><span data-stu-id="c8a4a-512">City</span></span>            | <span data-ttu-id="c8a4a-513">Cidade</span><span class="sxs-lookup"><span data-stu-id="c8a4a-513">City</span></span>                  |
| <span data-ttu-id="c8a4a-514">Região</span><span class="sxs-lookup"><span data-stu-id="c8a4a-514">County</span></span>          | <span data-ttu-id="c8a4a-515">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-515">County (Municipality)</span></span> |
| <span data-ttu-id="c8a4a-516">Rua</span><span class="sxs-lookup"><span data-stu-id="c8a4a-516">Street</span></span>          | <span data-ttu-id="c8a4a-517">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="c8a4a-517">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="c8a4a-518">Regiões fiscais</span><span class="sxs-lookup"><span data-stu-id="c8a4a-518">Tax regions</span></span>

<span data-ttu-id="c8a4a-519">Regiões fiscais são usadas para determinar os impostos apropriados a serem aplicados durante a geração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-519">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="c8a4a-520">As regiões fiscais são mapeadas para o Dayforce como endereços de localização.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-520">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="c8a4a-521">A região fiscal padrão deve estar associada à posição ativa do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-521">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="c8a4a-522">Região fiscal (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-522">Tax region (required)</span></span>
- <span data-ttu-id="c8a4a-523">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-523">Country/Region (required)</span></span>
- <span data-ttu-id="c8a4a-524">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-524">State (required)</span></span>
- <span data-ttu-id="c8a4a-525">Região</span><span class="sxs-lookup"><span data-stu-id="c8a4a-525">County</span></span> 
- <span data-ttu-id="c8a4a-526">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-526">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="c8a4a-527">Configurar seus dados para gerar folha de pagamento no México</span><span class="sxs-lookup"><span data-stu-id="c8a4a-527">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="c8a4a-528">Se você está gerando pagamento para funcionários no México, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="c8a4a-528">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="c8a4a-529">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-529">Departments are required on positions.</span></span>
- <span data-ttu-id="c8a4a-530">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-530">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="c8a4a-531">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="c8a4a-531">Job types</span></span>

<span data-ttu-id="c8a4a-532">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-532">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="c8a4a-533">Tipos de trabalho são necessários para processar a folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-533">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="c8a4a-534">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-534">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="c8a4a-535">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-535">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="c8a4a-536">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-536">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="c8a4a-537">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c8a4a-537">Job type</span></span>   | <span data-ttu-id="c8a4a-538">descrição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-538">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="c8a4a-539">Por hora</span><span class="sxs-lookup"><span data-stu-id="c8a4a-539">Hourly</span></span>     | <span data-ttu-id="c8a4a-540">MX por hora</span><span class="sxs-lookup"><span data-stu-id="c8a4a-540">MX Hourly</span></span>   |
| <span data-ttu-id="c8a4a-541">Assalariado</span><span class="sxs-lookup"><span data-stu-id="c8a4a-541">Salaried</span></span>   | <span data-ttu-id="c8a4a-542">MX assalariado</span><span class="sxs-lookup"><span data-stu-id="c8a4a-542">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="c8a4a-543">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-543">Position types</span></span> 

<span data-ttu-id="c8a4a-544">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-544">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="c8a4a-545">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-545">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="c8a4a-546">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-546">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="c8a4a-547">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-547">Position type</span></span>   | <span data-ttu-id="c8a4a-548">descrição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-548">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="c8a4a-549">Horário integral</span><span class="sxs-lookup"><span data-stu-id="c8a4a-549">Full-time</span></span>       | <span data-ttu-id="c8a4a-550">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="c8a4a-550">Full time employee</span></span> |
| <span data-ttu-id="c8a4a-551">Meio período</span><span class="sxs-lookup"><span data-stu-id="c8a4a-551">Part-time</span></span>       | <span data-ttu-id="c8a4a-552">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="c8a4a-552">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="c8a4a-553">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-553">Reason codes</span></span>

<span data-ttu-id="c8a4a-554">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-554">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="c8a4a-555">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-555">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="c8a4a-556">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-556">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="c8a4a-557">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="c8a4a-557">Reason code</span></span>            | <span data-ttu-id="c8a4a-558">descrição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-558">Description</span></span>                    | <span data-ttu-id="c8a4a-559">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="c8a4a-559">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="c8a4a-560">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="c8a4a-560">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="c8a4a-561">Partida antes da primeira folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="c8a4a-561">Departure before first payroll</span></span> | <span data-ttu-id="c8a4a-562">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-562">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-563">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="c8a4a-563">RESIGNATION</span></span>            | <span data-ttu-id="c8a4a-564">Demissão</span><span class="sxs-lookup"><span data-stu-id="c8a4a-564">Resignation</span></span>                    | <span data-ttu-id="c8a4a-565">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-565">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-566">PENSION</span><span class="sxs-lookup"><span data-stu-id="c8a4a-566">PENSION</span></span>                | <span data-ttu-id="c8a4a-567">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="c8a4a-567">Pension</span></span>                        | <span data-ttu-id="c8a4a-568">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-568">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-569">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="c8a4a-569">TERMINATION</span></span>            | <span data-ttu-id="c8a4a-570">Finalização</span><span class="sxs-lookup"><span data-stu-id="c8a4a-570">Termination</span></span>                    | <span data-ttu-id="c8a4a-571">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-571">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-572">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="c8a4a-572">RETIREMENT</span></span>             | <span data-ttu-id="c8a4a-573">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="c8a4a-573">Retirement</span></span>                     | <span data-ttu-id="c8a4a-574">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-574">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-575">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="c8a4a-575">ABSENTEE</span></span>               | <span data-ttu-id="c8a4a-576">Absentista</span><span class="sxs-lookup"><span data-stu-id="c8a4a-576">Absentee</span></span>                       | <span data-ttu-id="c8a4a-577">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-577">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-578">OTHER</span><span class="sxs-lookup"><span data-stu-id="c8a4a-578">OTHER</span></span>                  | <span data-ttu-id="c8a4a-579">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-579">Other Reasons</span></span>                  | <span data-ttu-id="c8a4a-580">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-580">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-581">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="c8a4a-581">CLOSURE</span></span>                | <span data-ttu-id="c8a4a-582">Fechamento da empresa</span><span class="sxs-lookup"><span data-stu-id="c8a4a-582">Business Closure</span></span>               | <span data-ttu-id="c8a4a-583">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-583">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-584">DEATH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-584">DEATH</span></span>                  | <span data-ttu-id="c8a4a-585">Morte</span><span class="sxs-lookup"><span data-stu-id="c8a4a-585">Death</span></span>                          | <span data-ttu-id="c8a4a-586">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-586">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-587">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="c8a4a-587">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="c8a4a-588">Licença</span><span class="sxs-lookup"><span data-stu-id="c8a4a-588">Leave of Absence</span></span>               | <span data-ttu-id="c8a4a-589">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-589">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-590">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="c8a4a-590">CONTRACTEND</span></span>            | <span data-ttu-id="c8a4a-591">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="c8a4a-591">End of Contract</span></span>                | <span data-ttu-id="c8a4a-592">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="c8a4a-592">Terminate worker</span></span>     |
| <span data-ttu-id="c8a4a-593">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="c8a4a-593">SALARYCHANGE</span></span>           | <span data-ttu-id="c8a4a-594">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="c8a4a-594">Change of Salary</span></span>               | <span data-ttu-id="c8a4a-595">Remuneração</span><span class="sxs-lookup"><span data-stu-id="c8a4a-595">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="c8a4a-596">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="c8a4a-596">Terms of employment</span></span>

<span data-ttu-id="c8a4a-597">Termos de emprego são usados para criar categorias de termos de emprego.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-597">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="c8a4a-598">Os termos são mapeados para o Dayforce como valores de indicador de emprego.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-598">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="c8a4a-599">Os termos de emprego e as descrições a seguir são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-599">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="c8a4a-600">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="c8a4a-600">Terms of employment</span></span>   | <span data-ttu-id="c8a4a-601">descrição</span><span class="sxs-lookup"><span data-stu-id="c8a4a-601">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="c8a4a-602">Normal</span><span class="sxs-lookup"><span data-stu-id="c8a4a-602">Regular</span></span>               | <span data-ttu-id="c8a4a-603">Normal</span><span class="sxs-lookup"><span data-stu-id="c8a4a-603">Regular</span></span>     |
| <span data-ttu-id="c8a4a-604">Direto</span><span class="sxs-lookup"><span data-stu-id="c8a4a-604">Direct</span></span>                | <span data-ttu-id="c8a4a-605">Direto</span><span class="sxs-lookup"><span data-stu-id="c8a4a-605">Direct</span></span>      |
| <span data-ttu-id="c8a4a-606">Estágio</span><span class="sxs-lookup"><span data-stu-id="c8a4a-606">Internship</span></span>            | <span data-ttu-id="c8a4a-607">Estágio</span><span class="sxs-lookup"><span data-stu-id="c8a4a-607">Internship</span></span>  |
| <span data-ttu-id="c8a4a-608">Permanente</span><span class="sxs-lookup"><span data-stu-id="c8a4a-608">Permanent</span></span>             | <span data-ttu-id="c8a4a-609">Permanente</span><span class="sxs-lookup"><span data-stu-id="c8a4a-609">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="c8a4a-610">Estado civil</span><span class="sxs-lookup"><span data-stu-id="c8a4a-610">Marital status</span></span>

<span data-ttu-id="c8a4a-611">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-611">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="c8a4a-612">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-612">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="c8a4a-613">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-613">Talent</span></span>                 | <span data-ttu-id="c8a4a-614">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-614">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="c8a4a-615">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-615">Married</span></span>                | <span data-ttu-id="c8a4a-616">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-616">Married</span></span>                   |
| <span data-ttu-id="c8a4a-617">Única</span><span class="sxs-lookup"><span data-stu-id="c8a4a-617">Single</span></span>                 | <span data-ttu-id="c8a4a-618">Única</span><span class="sxs-lookup"><span data-stu-id="c8a4a-618">Single</span></span>                    |
| <span data-ttu-id="c8a4a-619">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-619">Widowed</span></span>                | <span data-ttu-id="c8a4a-620">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-620">Widowed</span></span>                   |
| <span data-ttu-id="c8a4a-621">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-621">Divorced</span></span>               | <span data-ttu-id="c8a4a-622">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-622">Divorced</span></span>                  |
| <span data-ttu-id="c8a4a-623">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="c8a4a-623">Registered Partnership</span></span> | <span data-ttu-id="c8a4a-624">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="c8a4a-624">Domestic Partnership</span></span>      |
| <span data-ttu-id="c8a4a-625">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-625">None</span></span>                   | <span data-ttu-id="c8a4a-626">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="c8a4a-626">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="c8a4a-627">Coabitando</span><span class="sxs-lookup"><span data-stu-id="c8a4a-627">Cohabiting</span></span>             | <span data-ttu-id="c8a4a-628">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="c8a4a-628">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="c8a4a-629">Sexo</span><span class="sxs-lookup"><span data-stu-id="c8a4a-629">Gender</span></span>

<span data-ttu-id="c8a4a-630">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-630">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="c8a4a-631">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-631">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="c8a4a-632">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-632">Talent</span></span>       | <span data-ttu-id="c8a4a-633">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-633">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="c8a4a-634">Masculino</span><span class="sxs-lookup"><span data-stu-id="c8a4a-634">Male</span></span>         | <span data-ttu-id="c8a4a-635">Masculino</span><span class="sxs-lookup"><span data-stu-id="c8a4a-635">Male</span></span>                      |
| <span data-ttu-id="c8a4a-636">Feminino</span><span class="sxs-lookup"><span data-stu-id="c8a4a-636">Female</span></span>       | <span data-ttu-id="c8a4a-637">Feminino</span><span class="sxs-lookup"><span data-stu-id="c8a4a-637">Female</span></span>                    |
| <span data-ttu-id="c8a4a-638">Não específico</span><span class="sxs-lookup"><span data-stu-id="c8a4a-638">Non-specific</span></span> | <span data-ttu-id="c8a4a-639">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="c8a4a-639">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="c8a4a-640">Forma de pagamento</span><span class="sxs-lookup"><span data-stu-id="c8a4a-640">Payment method</span></span>

<span data-ttu-id="c8a4a-641">Os métodos de pagamento dão ao funcionário e à empresa uma maneira de descrever como os funcionários serão pagos.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-641">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="c8a4a-642">Os métodos de pagamento são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-642">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="c8a4a-643">A tabela a seguir mostra como os métodos de pagamento são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-643">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="c8a4a-644">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-644">Talent</span></span>             | <span data-ttu-id="c8a4a-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-645">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="c8a4a-646">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="c8a4a-646">Cash</span></span>               | <span data-ttu-id="c8a4a-647">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="c8a4a-647">Cash</span></span>                      |
| <span data-ttu-id="c8a4a-648">Pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="c8a4a-648">Electronic Payment</span></span> | <span data-ttu-id="c8a4a-649">Transferência</span><span class="sxs-lookup"><span data-stu-id="c8a4a-649">Transfer</span></span>                  |
| <span data-ttu-id="c8a4a-650">Verificação</span><span class="sxs-lookup"><span data-stu-id="c8a4a-650">Check</span></span>              | <span data-ttu-id="c8a4a-651">Cheque</span><span class="sxs-lookup"><span data-stu-id="c8a4a-651">Cheque</span></span>                    |
| <span data-ttu-id="c8a4a-652">Boleto bancário</span><span class="sxs-lookup"><span data-stu-id="c8a4a-652">Bank Draft</span></span>         | <span data-ttu-id="c8a4a-653">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="c8a4a-653">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="c8a4a-654">Outros</span><span class="sxs-lookup"><span data-stu-id="c8a4a-654">Other</span></span>              | <span data-ttu-id="c8a4a-655">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="c8a4a-655">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="c8a4a-656">Tipo de conta bancária</span><span class="sxs-lookup"><span data-stu-id="c8a4a-656">Bank account type</span></span>

<span data-ttu-id="c8a4a-657">Os tipos de conta bancária são usados para pagamentos eletrônicos aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-657">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="c8a4a-658">Os tipos de conta bancária são mapeados para o Dayforce como informações da conta de transferência.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-658">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="c8a4a-659">Os tipos de conta bancária são convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-659">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="c8a4a-660">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-660">Talent</span></span>            | <span data-ttu-id="c8a4a-661">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-661">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="c8a4a-662">Conta corrente</span><span class="sxs-lookup"><span data-stu-id="c8a4a-662">Checking Account</span></span>  | <span data-ttu-id="c8a4a-663">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="c8a4a-663">CheckingAccount</span></span>           |
| <span data-ttu-id="c8a4a-664">Conta-salário</span><span class="sxs-lookup"><span data-stu-id="c8a4a-664">Payroll Account</span></span>   | <span data-ttu-id="c8a4a-665">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="c8a4a-665">PayrollAccount</span></span>            |
| <span data-ttu-id="c8a4a-666">Conta de poupança</span><span class="sxs-lookup"><span data-stu-id="c8a4a-666">Savings Account</span></span>   | <span data-ttu-id="c8a4a-667">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="c8a4a-667">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="c8a4a-668">Conta BankGirot</span><span class="sxs-lookup"><span data-stu-id="c8a4a-668">BankGirot account</span></span> | <span data-ttu-id="c8a4a-669">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="c8a4a-669">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="c8a4a-670">Conta PlusGirot</span><span class="sxs-lookup"><span data-stu-id="c8a4a-670">PlusGirot account</span></span> | <span data-ttu-id="c8a4a-671">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="c8a4a-671">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="c8a4a-672">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="c8a4a-672">Earning codes</span></span>

<span data-ttu-id="c8a4a-673">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-673">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="c8a4a-674">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-674">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="c8a4a-675">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-675">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="c8a4a-676">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="c8a4a-676">Supported frequencies</span></span>

- <span data-ttu-id="c8a4a-677">Todas</span><span class="sxs-lookup"><span data-stu-id="c8a4a-677">All</span></span>
- <span data-ttu-id="c8a4a-678">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="c8a4a-678">EVERYPAY</span></span>
- <span data-ttu-id="c8a4a-679">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="c8a4a-679">EACHPAYPERIOD</span></span>
- <span data-ttu-id="c8a4a-680">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="c8a4a-680">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="c8a4a-681">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="c8a4a-681">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="c8a4a-682">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-682">1OFMTH</span></span>
- <span data-ttu-id="c8a4a-683">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-683">LASTOFMTH</span></span>
- <span data-ttu-id="c8a4a-684">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-684">2OFMTH</span></span>
- <span data-ttu-id="c8a4a-685">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-685">3OFMTH</span></span>
- <span data-ttu-id="c8a4a-686">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-686">4OFMTH</span></span>
- <span data-ttu-id="c8a4a-687">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-687">5OFMTH</span></span>
- <span data-ttu-id="c8a4a-688">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-688">1N2OFMTH</span></span>
- <span data-ttu-id="c8a4a-689">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-689">3N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-690">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-690">1N3OFMTH</span></span>
- <span data-ttu-id="c8a4a-691">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-691">1N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-692">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-692">2N3OFMTH</span></span>
- <span data-ttu-id="c8a4a-693">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-693">2N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-694">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-694">1N2N3OFMTH</span></span>
- <span data-ttu-id="c8a4a-695">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-695">1N2N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-696">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-696">1N3N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-697">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-697">2N3N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="c8a4a-698">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="c8a4a-699">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="c8a4a-699">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="c8a4a-700">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-700">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="c8a4a-701">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-701">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="c8a4a-702">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-702">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="c8a4a-703">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-703">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="c8a4a-704">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-704">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="c8a4a-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="c8a4a-705">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="c8a4a-706">Endereços</span><span class="sxs-lookup"><span data-stu-id="c8a4a-706">Addresses</span></span>

<span data-ttu-id="c8a4a-707">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-707">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="c8a4a-708">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-708">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="c8a4a-709">Talent</span><span class="sxs-lookup"><span data-stu-id="c8a4a-709">Talent</span></span>              | <span data-ttu-id="c8a4a-710">Dayforce</span><span class="sxs-lookup"><span data-stu-id="c8a4a-710">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="c8a4a-711">País/Região</span><span class="sxs-lookup"><span data-stu-id="c8a4a-711">Country/Region</span></span>      | <span data-ttu-id="c8a4a-712">Código do País</span><span class="sxs-lookup"><span data-stu-id="c8a4a-712">Country Code</span></span>          |
| <span data-ttu-id="c8a4a-713">CEP</span><span class="sxs-lookup"><span data-stu-id="c8a4a-713">Zip/Postal Code</span></span>     | <span data-ttu-id="c8a4a-714">CEP</span><span class="sxs-lookup"><span data-stu-id="c8a4a-714">Postal Code</span></span>           |
| <span data-ttu-id="c8a4a-715">Estadual</span><span class="sxs-lookup"><span data-stu-id="c8a4a-715">State</span></span>               | <span data-ttu-id="c8a4a-716">Código de estado</span><span class="sxs-lookup"><span data-stu-id="c8a4a-716">State Code</span></span>            |
| <span data-ttu-id="c8a4a-717">Cidade</span><span class="sxs-lookup"><span data-stu-id="c8a4a-717">City</span></span>                | <span data-ttu-id="c8a4a-718">Cidade</span><span class="sxs-lookup"><span data-stu-id="c8a4a-718">City</span></span>                  |
| <span data-ttu-id="c8a4a-719">Região</span><span class="sxs-lookup"><span data-stu-id="c8a4a-719">County</span></span>              | <span data-ttu-id="c8a4a-720">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="c8a4a-720">County (Municipality)</span></span> |
| <span data-ttu-id="c8a4a-721">Rua</span><span class="sxs-lookup"><span data-stu-id="c8a4a-721">Street</span></span>              | <span data-ttu-id="c8a4a-722">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="c8a4a-722">Address Line 1</span></span>        |
| <span data-ttu-id="c8a4a-723">Número</span><span class="sxs-lookup"><span data-stu-id="c8a4a-723">Street Number</span></span>       | <span data-ttu-id="c8a4a-724">Linha de endereço 2</span><span class="sxs-lookup"><span data-stu-id="c8a4a-724">Address Line 2</span></span>        |
| <span data-ttu-id="c8a4a-725">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="c8a4a-725">Building Complement</span></span> | <span data-ttu-id="c8a4a-726">Linha de endereço 5</span><span class="sxs-lookup"><span data-stu-id="c8a4a-726">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="c8a4a-727">Número do passaporte</span><span class="sxs-lookup"><span data-stu-id="c8a4a-727">Passport number</span></span>

<span data-ttu-id="c8a4a-728">Os funcionários podem declarar as informações do passaporte.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-728">Employees can declare passport information.</span></span> <span data-ttu-id="c8a4a-729">Essas informações são do tipo de identificação **Passaporte** e estão integradas ao Dayforce como parte das informações específicas do México de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-729">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="c8a4a-730">Tipo de identificação = "Passaporte"</span><span class="sxs-lookup"><span data-stu-id="c8a4a-730">Identification Type = "Passport"</span></span>
- <span data-ttu-id="c8a4a-731">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="c8a4a-731">Issued Date</span></span>
- <span data-ttu-id="c8a4a-732">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="c8a4a-732">Expiration Date</span></span>

<span data-ttu-id="c8a4a-733">Os funcionários podem declarar vários números de identificação do tipo de identificação **Passaporte**.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-733">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="c8a4a-734">No entanto, apenas a entrada atual do passaporte ativo é integrada ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-734">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="c8a4a-735">Se todas as entradas do passaporte expirarem, o passaporte emitido mais recentemente será integrado ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="c8a4a-735">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
