---
title: Configurar integração com o Dayforce
description: A integração entre o Microsoft Dynamics 365 Human Resources e o Ceridian Dayforce depende de várias etapas de configuração descritas neste artigo. Você deve configurar a integração no Human Resources e no Dayforce antes de processar uma execução de pagamento.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c66ec772ea66732e042f50081f04a6569852f211
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431282"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="0489e-104">Configurar integração com o Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-104">Configure integration with Dayforce</span></span>

<span data-ttu-id="0489e-105">A integração entre o Microsoft Dynamics 365 Human Resources e o Ceridian Dayforce depende de várias etapas de configuração descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="0489e-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="0489e-106">Você deve configurar a integração no Human Resources e no Dayforce antes de processar uma execução de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0489e-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="0489e-107">Ao usar um serviço como o Dayforce para concluir execuções de pagamento, é necessário ativar a integração no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0489e-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="0489e-108">A integração requer dados específicos do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0489e-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="0489e-109">Portanto, você deve verificar se os dados mapeados para o Dayforce estão configurados no Human Resources de forma compatível com a integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="0489e-110">A integração usa as seguintes categorias amplas de dados:</span><span class="sxs-lookup"><span data-stu-id="0489e-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="0489e-111">Dados de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-111">Human resources data</span></span>
- <span data-ttu-id="0489e-112">Dados de remuneração</span><span class="sxs-lookup"><span data-stu-id="0489e-112">Compensation data</span></span>
- <span data-ttu-id="0489e-113">Dados da folha de pagamento, como ciclos de pagamento, períodos de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="0489e-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="0489e-114">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-114">Worker data</span></span>

<span data-ttu-id="0489e-115">Este artigo descreve as etapas que você deve seguir para ativar a integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="0489e-116">Também explica os tipos de dados e os detalhes de configuração que a integração requer.</span><span class="sxs-lookup"><span data-stu-id="0489e-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="0489e-117">Habilitar a integração</span><span class="sxs-lookup"><span data-stu-id="0489e-117">Enable the integration</span></span>

<span data-ttu-id="0489e-118">No Human Resources, você deve ativar a integração e inserir as informações de configuração para se conectar ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="0489e-119">Para que a transação de contabilidade produzida seja importada para o Microsoft Dynamics 365 Finance, também é preciso configurar uma conta de armazenamento do Microsoft Azure e inserir a cadeia de conexão do Armazenamento do Azure no Finance.</span><span class="sxs-lookup"><span data-stu-id="0489e-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="0489e-120">Para ativar a integração no Human Resources, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="0489e-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="0489e-121">Na página **Administração do sistema**, selecione **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="0489e-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="0489e-122">Digite o ponto de extremidade seguro do File Transfer Protocol (FTP) e o caminho seguro da pasta FTP.</span><span class="sxs-lookup"><span data-stu-id="0489e-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="0489e-123">Digite o nome e a senha do usuário que acessará o ponto de extremidade e o caminho da pasta seguros do FTP.</span><span class="sxs-lookup"><span data-stu-id="0489e-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="0489e-124">Teste a conexão, conforme necessário, e defina a opção **Habilitar integração da folha de pagamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="0489e-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="0489e-125">Quando a integração é ativada, o pacote e os arquivos de exportação de dados são criados e a frequência é configurada.</span><span class="sxs-lookup"><span data-stu-id="0489e-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="0489e-126">Você pode alterar essa frequência conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0489e-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="0489e-127">Para obter mais informações sobre as contas de armazenamento do Azure e as cadeias de conexão do Armazenamento do Azure, consulte os seguintes artigos do Azure:</span><span class="sxs-lookup"><span data-stu-id="0489e-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="0489e-128">Sobre as contas de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="0489e-128">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="0489e-129">Configurar cadeias de conexão do Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="0489e-129">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="0489e-130">Detalhes técnicos quando a integração da folha de pagamento está habilitada</span><span class="sxs-lookup"><span data-stu-id="0489e-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="0489e-131">A ativação da integração da folha de pagamento tem dois efeitos principais:</span><span class="sxs-lookup"><span data-stu-id="0489e-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="0489e-132">Um projeto de exportação de dados denominado "Exportação de integração da folha de pagamento" é criado.</span><span class="sxs-lookup"><span data-stu-id="0489e-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="0489e-133">Este projeto contém as entidades e os campos necessários para a integração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0489e-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="0489e-134">Para revisar o projeto, vá para **Administração do sistema**, selecione o bloco **Gerenciamento de dados** e abra o projeto de dados da lista de projetos.</span><span class="sxs-lookup"><span data-stu-id="0489e-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="0489e-135">Esse trabalho em lotes executa o projeto de exportação de dados, criptografa o pacote de dados resultante e transfere o arquivo do pacote de dados para a empresa de SFTP configurada na tela **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="0489e-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="0489e-136">O pacote de dados transferido para a empresa de SFTP é criptografado usando uma chave exclusiva para o pacote.</span><span class="sxs-lookup"><span data-stu-id="0489e-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="0489e-137">A chave é um Azure Key Vault acessível somente pelo Ceridian.</span><span class="sxs-lookup"><span data-stu-id="0489e-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="0489e-138">Não é possível descriptografar e revisar o conteúdo do pacote de dados.</span><span class="sxs-lookup"><span data-stu-id="0489e-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="0489e-139">Se você precisar examinar o conteúdo do pacote de dados, exporte manualmente o projeto de dados "Exportação de integração da folha de pagamento", baixe-o e abra-o</span><span class="sxs-lookup"><span data-stu-id="0489e-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="0489e-140">A exportação manual não aplicará a criptografia nem transferirá o pacote.</span><span class="sxs-lookup"><span data-stu-id="0489e-140">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="0489e-141">Configurar seus dados</span><span class="sxs-lookup"><span data-stu-id="0489e-141">Configure your data</span></span> 

<span data-ttu-id="0489e-142">Para processar a folha de pagamento, você deve configurar dados de RH no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0489e-142">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="0489e-143">Você deve configurar dados organizacionais, como cargos e posições, juntamente com informações sobre benefícios e remuneração.</span><span class="sxs-lookup"><span data-stu-id="0489e-143">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="0489e-144">Esses dados fornecem as informações de emprego, pagamento e dedução necessárias para gerar o pagamento do empregado.</span><span class="sxs-lookup"><span data-stu-id="0489e-144">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="0489e-145">Dados de RH</span><span class="sxs-lookup"><span data-stu-id="0489e-145">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="0489e-146">Benefícios</span><span class="sxs-lookup"><span data-stu-id="0489e-146">Benefits</span></span> 

<span data-ttu-id="0489e-147">O RH fornece ferramentas para a configuração e manutenção dos benefícios, deduções e planos de remuneração do trabalhador que uma organização oferece ou processa para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="0489e-147">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="0489e-148">Ao criar benefícios, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-148">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="0489e-149">Planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="0489e-149">Benefit plans</span></span>

- <span data-ttu-id="0489e-150">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-150">Plan (required)</span></span>
- <span data-ttu-id="0489e-151">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-151">Type (required)</span></span>
- <span data-ttu-id="0489e-152">Impacto da folha de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-152">Payroll impact (required)</span></span>
- <span data-ttu-id="0489e-153">Recuperar atrasos de pagamento</span><span class="sxs-lookup"><span data-stu-id="0489e-153">Recover arrears</span></span>
- <span data-ttu-id="0489e-154">Método de dedução</span><span class="sxs-lookup"><span data-stu-id="0489e-154">Deduction method</span></span>
- <span data-ttu-id="0489e-155">Prioridade da dedução</span><span class="sxs-lookup"><span data-stu-id="0489e-155">Deduction priority</span></span>
- <span data-ttu-id="0489e-156">Limitar período</span><span class="sxs-lookup"><span data-stu-id="0489e-156">Limit period</span></span>
- <span data-ttu-id="0489e-157">Valor de limite</span><span class="sxs-lookup"><span data-stu-id="0489e-157">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="0489e-158">Benefícios</span><span class="sxs-lookup"><span data-stu-id="0489e-158">Benefits</span></span>

- <span data-ttu-id="0489e-159">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-159">Plan (required)</span></span>
- <span data-ttu-id="0489e-160">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-160">Type (required)</span></span>
- <span data-ttu-id="0489e-161">Opção (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-161">Option (required)</span></span>
- <span data-ttu-id="0489e-162">ID do benefício (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-162">Benefit ID (required)</span></span>
- <span data-ttu-id="0489e-163">Frequência</span><span class="sxs-lookup"><span data-stu-id="0489e-163">Frequency</span></span>
- <span data-ttu-id="0489e-164">Base</span><span class="sxs-lookup"><span data-stu-id="0489e-164">Basis</span></span>
- <span data-ttu-id="0489e-165">Valor ou taxa</span><span class="sxs-lookup"><span data-stu-id="0489e-165">Amount or rate</span></span>
- <span data-ttu-id="0489e-166">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="0489e-166">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="0489e-167">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="0489e-167">Supported frequencies</span></span> 

- <span data-ttu-id="0489e-168">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="0489e-168">Weekly</span></span>
- <span data-ttu-id="0489e-169">Por quinzena</span><span class="sxs-lookup"><span data-stu-id="0489e-169">Bi-weekly</span></span>
- <span data-ttu-id="0489e-170">Quinzenal</span><span class="sxs-lookup"><span data-stu-id="0489e-170">Semi-monthly</span></span>
- <span data-ttu-id="0489e-171">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="0489e-171">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="0489e-172">Bases com suporte</span><span class="sxs-lookup"><span data-stu-id="0489e-172">Supported bases</span></span> 

- <span data-ttu-id="0489e-173">Valor fixo</span><span class="sxs-lookup"><span data-stu-id="0489e-173">Fixed amount</span></span>
- <span data-ttu-id="0489e-174">Percentual de ganhos</span><span class="sxs-lookup"><span data-stu-id="0489e-174">Percent of earnings</span></span>
- <span data-ttu-id="0489e-175">Horas produtivas</span><span class="sxs-lookup"><span data-stu-id="0489e-175">Productive hours</span></span>

<span data-ttu-id="0489e-176">O Dayforce cria as deduções a seguir, com base no impacto da folha de pagamento definido no plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="0489e-176">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="0489e-177">Seleção no Human Resources</span><span class="sxs-lookup"><span data-stu-id="0489e-177">Selection in Human Resources</span></span>        | <span data-ttu-id="0489e-178">Resultado no Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-178">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="0489e-179">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="0489e-179">None</span></span>                       | <span data-ttu-id="0489e-180">Nenhuma dedução é criada.</span><span class="sxs-lookup"><span data-stu-id="0489e-180">No deduction is created.</span></span>                      |
| <span data-ttu-id="0489e-181">Somente dedução</span><span class="sxs-lookup"><span data-stu-id="0489e-181">Deduction only</span></span>             | <span data-ttu-id="0489e-182">Uma dedução de funcionário é criada.</span><span class="sxs-lookup"><span data-stu-id="0489e-182">An employee deduction is created.</span></span>             |
| <span data-ttu-id="0489e-183">Somente contribuição</span><span class="sxs-lookup"><span data-stu-id="0489e-183">Contribution only</span></span>          | <span data-ttu-id="0489e-184">Uma dedução de empregador é criada.</span><span class="sxs-lookup"><span data-stu-id="0489e-184">An employer deduction is created.</span></span>             |
| <span data-ttu-id="0489e-185">Dedução e contribuição</span><span class="sxs-lookup"><span data-stu-id="0489e-185">Deduction and contribution</span></span> | <span data-ttu-id="0489e-186">Deduções de funcionário e empregador são criadas.</span><span class="sxs-lookup"><span data-stu-id="0489e-186">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="0489e-187">Para obter mais informações sobre como definir e gerenciar um programa de benefícios, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="0489e-187">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="0489e-188">Entregar um programa de benefícios para funcionários</span><span class="sxs-lookup"><span data-stu-id="0489e-188">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="0489e-189">Criar um novo benefício</span><span class="sxs-lookup"><span data-stu-id="0489e-189">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="0489e-190">Definir regras e políticas de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="0489e-190">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="0489e-191">Inscrever e remover benefícios de trabalhadores</span><span class="sxs-lookup"><span data-stu-id="0489e-191">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="0489e-192">Remuneração</span><span class="sxs-lookup"><span data-stu-id="0489e-192">Compensation</span></span> 

<span data-ttu-id="0489e-193">O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios.</span><span class="sxs-lookup"><span data-stu-id="0489e-193">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="0489e-194">Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos.</span><span class="sxs-lookup"><span data-stu-id="0489e-194">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="0489e-195">O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="0489e-195">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="0489e-196">O Dayforce usa informações de remuneração para calcular a taxa por hora ou anual de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="0489e-196">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="0489e-197">Planos de remuneração fixa e conversões de taxa de pagamento são necessários.</span><span class="sxs-lookup"><span data-stu-id="0489e-197">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="0489e-198">Os funcionários devem estar associados a um plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="0489e-198">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="0489e-199">Para obter mais informações sobre planos de compensação, veja os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="0489e-199">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="0489e-200">Criar planos de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="0489e-200">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="0489e-201">Criar planos de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="0489e-201">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="0489e-202">Desenvolver estrutura e planos de remuneração/salário</span><span class="sxs-lookup"><span data-stu-id="0489e-202">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="0489e-203">Processar remuneração</span><span class="sxs-lookup"><span data-stu-id="0489e-203">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="0489e-204">Definir processo de remuneração e calcular resultados</span><span class="sxs-lookup"><span data-stu-id="0489e-204">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="0489e-205">Inscrever um funcionário em um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="0489e-205">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="0489e-206">Inscrever um funcionário em um plano de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="0489e-206">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="0489e-207">Trabalhos</span><span class="sxs-lookup"><span data-stu-id="0489e-207">Jobs</span></span> 

<span data-ttu-id="0489e-208">Um trabalho é um conjunto de tarefas e responsabilidades exigidas de uma pessoa que realiza um trabalho.</span><span class="sxs-lookup"><span data-stu-id="0489e-208">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="0489e-209">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="0489e-209">For more information, see the following articles:</span></span>

- [<span data-ttu-id="0489e-210">Configurando os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="0489e-210">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="0489e-211">Definir novos trabalhos</span><span class="sxs-lookup"><span data-stu-id="0489e-211">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="0489e-212">Cargos</span><span class="sxs-lookup"><span data-stu-id="0489e-212">Positions</span></span>

<span data-ttu-id="0489e-213">Um cargo é uma instância individual de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="0489e-213">A position is an individual instance of a job.</span></span> <span data-ttu-id="0489e-214">Por exemplo, a posição "Gerente de vendas (Leste)" é uma das posições associadas ao trabalho "Gerente de vendas".</span><span class="sxs-lookup"><span data-stu-id="0489e-214">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="0489e-215">Uma posição existe em um departamento.</span><span class="sxs-lookup"><span data-stu-id="0489e-215">A position exists in a department.</span></span> <span data-ttu-id="0489e-216">Apenas um trabalhador pode ser associado a cada posição.</span><span class="sxs-lookup"><span data-stu-id="0489e-216">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="0489e-217">Considere os seguintes dados e configurações ao configurar as posições:</span><span class="sxs-lookup"><span data-stu-id="0489e-217">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="0489e-218">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-218">Position (required)</span></span>
- <span data-ttu-id="0489e-219">Descrição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-219">Description (required)</span></span>
- <span data-ttu-id="0489e-220">Trabalho (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-220">Job (required)</span></span>
- <span data-ttu-id="0489e-221">Departamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-221">Department (required)</span></span>
- <span data-ttu-id="0489e-222">Tipo de posição (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-222">Position type (required)</span></span>
- <span data-ttu-id="0489e-223">Equivalente ao horário integral</span><span class="sxs-lookup"><span data-stu-id="0489e-223">Full-time equivalent</span></span>
- <span data-ttu-id="0489e-224">Horas normais anuais (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="0489e-224">Annual regular hours (required)</span></span>
- <span data-ttu-id="0489e-225">Pago por entidade legal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-225">Paid by legal entity (required)</span></span>
- <span data-ttu-id="0489e-226">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-226">Pay cycle (required)</span></span>
- <span data-ttu-id="0489e-227">Dimensão financeira padrão – Centro de custo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-227">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="0489e-228">Atribuição do trabalhador – Trabalhador, início da atribuição, fim da atribuição, código de motivo</span><span class="sxs-lookup"><span data-stu-id="0489e-228">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="0489e-229">Se várias posições no mesmo departamento estiverem associadas ao mesmo trabalho, elas serão consolidadas em uma única posição no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-229">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="0489e-230">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="0489e-230">For more information, see the following articles:</span></span>

- [<span data-ttu-id="0489e-231">Organizar sua força de trabalho usando departamentos, trabalhos e posições</span><span class="sxs-lookup"><span data-stu-id="0489e-231">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="0489e-232">Configurar posições</span><span class="sxs-lookup"><span data-stu-id="0489e-232">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="0489e-233">Departamentos</span><span class="sxs-lookup"><span data-stu-id="0489e-233">Departments</span></span>

<span data-ttu-id="0489e-234">Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização.</span><span class="sxs-lookup"><span data-stu-id="0489e-234">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="0489e-235">Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="0489e-235">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="0489e-236">Você pode usar departamentos para relatar áreas funcionais.</span><span class="sxs-lookup"><span data-stu-id="0489e-236">You can use departments to report on functional areas.</span></span> <span data-ttu-id="0489e-237">Os departamentos podem ter a responsabilidade de lucros e perdas.</span><span class="sxs-lookup"><span data-stu-id="0489e-237">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="0489e-238">Para obter mais informações, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="0489e-238">For more information, see the following articles:</span></span>

- [<span data-ttu-id="0489e-239">Criar um departamento e associá-lo à hierarquia de departamentos</span><span class="sxs-lookup"><span data-stu-id="0489e-239">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="0489e-240">Definir novos departamentos</span><span class="sxs-lookup"><span data-stu-id="0489e-240">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="0489e-241">Ciclos de pagamento e períodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="0489e-241">Pay cycles and pay periods</span></span>

<span data-ttu-id="0489e-242">Um ciclo de pagamento determina a frequência com que a folha de pagamento é executada e os dias específicos em que os trabalhadores são pagos.</span><span class="sxs-lookup"><span data-stu-id="0489e-242">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="0489e-243">Por exemplo, um ciclo de pagamento pode ser mensal e os funcionários podem ser pagos no último dia do mês.</span><span class="sxs-lookup"><span data-stu-id="0489e-243">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="0489e-244">Como alternativa, um ciclo de pagamento pode ser semanal e os funcionários podem ser pagos na terça-feira após o término do período de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0489e-244">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="0489e-245">Ciclos de pagamento são atribuídos a posições para controlar quando os trabalhadores nessas posições são pagos.</span><span class="sxs-lookup"><span data-stu-id="0489e-245">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="0489e-246">Após a criação dos ciclos de pagamento, você pode gerar períodos de pagamento para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="0489e-246">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="0489e-247">Cada período de pagamento inclui uma data de pagamento padrão baseada nas informações que você fornece.</span><span class="sxs-lookup"><span data-stu-id="0489e-247">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="0489e-248">No entanto, você pode modificar a data de pagamento padrão em um período de pagamento para permitir exceções (por exemplo, quando a data de pagamento cai em um feriado).</span><span class="sxs-lookup"><span data-stu-id="0489e-248">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="0489e-249">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="0489e-249">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="0489e-250">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-250">Pay cycle (required)</span></span>
- <span data-ttu-id="0489e-251">Frequência do ciclo de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-251">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="0489e-252">Data de início do período (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-252">Period start date (first pay period required)</span></span>
- <span data-ttu-id="0489e-253">Data de pagamento padrão (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-253">Default payment date (first pay period required)</span></span>

<span data-ttu-id="0489e-254">Essas informações são integradas ao Dayforce como grupos de pagamento e são separadas por país ou região para cada ciclo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0489e-254">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="0489e-255">Pelo menos um período de pagamento deve ser gerado antes da integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-255">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="0489e-256">O Dayforce gera datas de pagamento e calendários do grupo de pagamento, com base na data de início do primeiro período de pagamento e na data de pagamento padrão configurada no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0489e-256">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="0489e-257">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="0489e-257">Earning codes</span></span>

<span data-ttu-id="0489e-258">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="0489e-258">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="0489e-259">Os códigos têm vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="0489e-259">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="0489e-260">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="0489e-260">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="0489e-261">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-261">Earning Code (required)</span></span>
- <span data-ttu-id="0489e-262">descrição</span><span class="sxs-lookup"><span data-stu-id="0489e-262">Description</span></span>
- <span data-ttu-id="0489e-263">Unidade de medida</span><span class="sxs-lookup"><span data-stu-id="0489e-263">Unit of measure</span></span>
- <span data-ttu-id="0489e-264">Produtivo</span><span class="sxs-lookup"><span data-stu-id="0489e-264">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="0489e-265">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-265">Worker data</span></span>

<span data-ttu-id="0489e-266">Os registros dos vários tipos de trabalhadores que você tem são importantes para o RH e sistemas de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0489e-266">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="0489e-267">As informações inseridas podem ser usadas para rastrear trabalhadores e informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="0489e-267">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="0489e-268">Você pode manter estas informações para trabalhadores:</span><span class="sxs-lookup"><span data-stu-id="0489e-268">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="0489e-269">**Básicas** – mantenha informações básicas do trabalhador, como informações de contato, demográficas, de identificação, sobre a família, o status de serviço militar, informações de exilado, contatos pessoais e de emergência.</span><span class="sxs-lookup"><span data-stu-id="0489e-269">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="0489e-270">**Emprego** – mantenha informações sobre o emprego dos trabalhadores, como a afiliação da empresa ou organização, a atribuição de posição, as datas inicial e final, a qualificação para trabalho, o contrato de trabalho, a pensão, férias e as informações de mudança.</span><span class="sxs-lookup"><span data-stu-id="0489e-270">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="0489e-271">**Licença e ausência** – mantenha informações sobre as ausências dos trabalhadores, como o calendário de trabalho, as transações de ausência e a configuração de ausência.</span><span class="sxs-lookup"><span data-stu-id="0489e-271">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="0489e-272">**Remuneração e folha de pagamento** – mantenha informações sobre os planos de remuneração e as informações de folha de pagamento de trabalhadores, como o registro do plano, prêmios, o desempenho, a comissão, informações sobre impostos, aposentadoria e deduções do salário.</span><span class="sxs-lookup"><span data-stu-id="0489e-272">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="0489e-273">Ao inserir informações do trabalhador, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-273">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="0489e-274">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="0489e-274">General information</span></span>

- <span data-ttu-id="0489e-275">Número de equipe (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-275">Personnel number (required)</span></span>
- <span data-ttu-id="0489e-276">Nome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-276">First name (required)</span></span>
- <span data-ttu-id="0489e-277">Sobrenome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-277">Last name (required)</span></span>
- <span data-ttu-id="0489e-278">Nome do meio</span><span class="sxs-lookup"><span data-stu-id="0489e-278">Middle name</span></span>
- <span data-ttu-id="0489e-279">Aniversário de tempo de serviço</span><span class="sxs-lookup"><span data-stu-id="0489e-279">Seniority date</span></span>
- <span data-ttu-id="0489e-280">Conhecido como</span><span class="sxs-lookup"><span data-stu-id="0489e-280">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="0489e-281">Informações pessoais</span><span class="sxs-lookup"><span data-stu-id="0489e-281">Personal information</span></span>

- <span data-ttu-id="0489e-282">Estado civil (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-282">Marital status (required)</span></span>
- <span data-ttu-id="0489e-283">Data de nascimento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-283">Birth date (required)</span></span>
- <span data-ttu-id="0489e-284">Sexo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-284">Gender (required)</span></span>
- <span data-ttu-id="0489e-285">Pessoa portadora de deficiências</span><span class="sxs-lookup"><span data-stu-id="0489e-285">Person with disabilities</span></span>
- <span data-ttu-id="0489e-286">Região do país de nacionalidade (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="0489e-286">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="0489e-287">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="0489e-287">Address information</span></span>

- <span data-ttu-id="0489e-288">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-288">Primary (required)</span></span>
- <span data-ttu-id="0489e-289">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-289">Country/region (required)</span></span>
- <span data-ttu-id="0489e-290">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-290">Postal code (required)</span></span>
- <span data-ttu-id="0489e-291">Número da rua (obrigatório) (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="0489e-291">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="0489e-292">Complemento do edifício (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="0489e-292">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="0489e-293">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-293">City (required)</span></span>
- <span data-ttu-id="0489e-294">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-294">State (required)</span></span>
- <span data-ttu-id="0489e-295">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-295">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="0489e-296">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="0489e-296">Contact information</span></span> 

- <span data-ttu-id="0489e-297">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-297">Primary (required)</span></span>
- <span data-ttu-id="0489e-298">Número de contato (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-298">Contact number (required)</span></span>
- <span data-ttu-id="0489e-299">Extensão</span><span class="sxs-lookup"><span data-stu-id="0489e-299">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="0489e-300">Informações sobre folha de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="0489e-300">Payroll information and earning codes</span></span>

<span data-ttu-id="0489e-301">Os funcionários podem receber ganhos específicos com uma determinada frequência de pagamento e ter um método de pagamento preferencial.</span><span class="sxs-lookup"><span data-stu-id="0489e-301">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="0489e-302">Os campos a seguir são usados no Dayforce para ajudar a garantir que essas preferências e configurações sejam usadas.</span><span class="sxs-lookup"><span data-stu-id="0489e-302">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="0489e-303">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="0489e-303">Earning codes</span></span>

- <span data-ttu-id="0489e-304">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-304">Position (required)</span></span>
- <span data-ttu-id="0489e-305">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-305">Earning Code (required)</span></span>
- <span data-ttu-id="0489e-306">Frequência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-306">Frequency (required)</span></span>
- <span data-ttu-id="0489e-307">Valor (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-307">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="0489e-308">Informações da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="0489e-308">Payroll information</span></span>

- <span data-ttu-id="0489e-309">Método de Pagamento</span><span class="sxs-lookup"><span data-stu-id="0489e-309">Payment Method</span></span>
- <span data-ttu-id="0489e-310">Região econômica (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-310">Economic Region (required)</span></span>
- <span data-ttu-id="0489e-311">ID de Benefícios do Funcionário</span><span class="sxs-lookup"><span data-stu-id="0489e-311">Employee Benefits ID</span></span>
- <span data-ttu-id="0489e-312">Número de ID nacional (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-312">National ID Number (required)</span></span>
- <span data-ttu-id="0489e-313">Número de serviço militar</span><span class="sxs-lookup"><span data-stu-id="0489e-313">Military Service Number</span></span>
- <span data-ttu-id="0489e-314">ID de turno (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-314">Shift ID (required)</span></span>
- <span data-ttu-id="0489e-315">Número fiscal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-315">Tax Number (required)</span></span>
- <span data-ttu-id="0489e-316">ID do sindicato (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-316">Union ID (required)</span></span>
- <span data-ttu-id="0489e-317">ID do dia útil (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-317">Work Day ID (required)</span></span>
- <span data-ttu-id="0489e-318">Número de autorização de trabalho</span><span class="sxs-lookup"><span data-stu-id="0489e-318">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="0489e-319">Para o método de pagamento, o México permite **Pagamento à vista**, **Cheque** (o cheque físico da empresa) e **Pagamento Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="0489e-319">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="0489e-320">Se nenhum método de pagamento for especificado, **Cheque** é usado por padrão.</span><span class="sxs-lookup"><span data-stu-id="0489e-320">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="0489e-321">Detalhes do emprego</span><span class="sxs-lookup"><span data-stu-id="0489e-321">Employment details</span></span>

<span data-ttu-id="0489e-322">O histórico de detalhes de emprego é usado como principal informação para derivar os status de contratação, rescisão e recontratação de um funcionário no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-322">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="0489e-323">O Dayforce suporta apenas um registro de emprego ativo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0489e-323">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="0489e-324">Data de início do emprego (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-324">Employment start date (required)</span></span>
- <span data-ttu-id="0489e-325">Data final do emprego</span><span class="sxs-lookup"><span data-stu-id="0489e-325">Employment end date</span></span>
- <span data-ttu-id="0489e-326">Data de início</span><span class="sxs-lookup"><span data-stu-id="0489e-326">Start date</span></span>
- <span data-ttu-id="0489e-327">Data inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="0489e-327">Adjusted start date</span></span>
- <span data-ttu-id="0489e-328">Data de rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="0489e-328">Termination date (required upon termination)</span></span>
- <span data-ttu-id="0489e-329">Motivo da rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="0489e-329">Termination reason (required upon termination)</span></span>

<span data-ttu-id="0489e-330">As principais datas de um funcionário são derivadas usando-se as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="0489e-330">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="0489e-331">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-331">Human Resources</span></span>                | <span data-ttu-id="0489e-332">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-332">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0489e-333">Data de contratação mais recente</span><span class="sxs-lookup"><span data-stu-id="0489e-333">Most recent hire date</span></span> | <span data-ttu-id="0489e-334">Início de emprego do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="0489e-334">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="0489e-335">Data da rescisão</span><span class="sxs-lookup"><span data-stu-id="0489e-335">Termination date</span></span>      | <span data-ttu-id="0489e-336">Data de rescisão do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="0489e-336">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="0489e-337">Data de início</span><span class="sxs-lookup"><span data-stu-id="0489e-337">Start date</span></span>            | <span data-ttu-id="0489e-338">Data de início ajustada, data de início ou início de emprego do registro histórico de emprego não ativo atual</span><span class="sxs-lookup"><span data-stu-id="0489e-338">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="0489e-339">Data original de contratação</span><span class="sxs-lookup"><span data-stu-id="0489e-339">Original hire date</span></span>    | <span data-ttu-id="0489e-340">Início de emprego do registro histórico de emprego mais antigo</span><span class="sxs-lookup"><span data-stu-id="0489e-340">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="0489e-341">Remuneração</span><span class="sxs-lookup"><span data-stu-id="0489e-341">Compensation</span></span>

<span data-ttu-id="0489e-342">Um plano de remuneração fixa deve estar associado à posição principal de cada funcionário durante um período de emprego.</span><span class="sxs-lookup"><span data-stu-id="0489e-342">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="0489e-343">Esse período tem início na data em que o funcionário foi contratado (ou na data de início do emprego) e continua até a rescisão.</span><span class="sxs-lookup"><span data-stu-id="0489e-343">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="0489e-344">Data de vigência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-344">Effective Date (required)</span></span>
- <span data-ttu-id="0489e-345">Data de vencimento</span><span class="sxs-lookup"><span data-stu-id="0489e-345">Expiration date</span></span>
- <span data-ttu-id="0489e-346">Taxa de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-346">Pay Rate (required)</span></span>
- <span data-ttu-id="0489e-347">Conversões de taxa de pagamento (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="0489e-347">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="0489e-348">Equivalente anual (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-348">Annual equivalent (required)</span></span>
- <span data-ttu-id="0489e-349">Equivalente por hora (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-349">Hourly equivalent (required)</span></span>

<span data-ttu-id="0489e-350">Se um funcionário por hora tiver várias posições, a remuneração fixa da posição principal é importada para o Dayforce como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="0489e-350">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="0489e-351">Para posições não principais, a taxa por hora é salva na posição correspondente no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-351">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="0489e-352">Se um funcionário assalariado tiver várias posições, a taxa acumulada de horas e o salário anual em todas as posições ativas serão derivados e usados como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="0489e-352">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="0489e-353">Números de identificação</span><span class="sxs-lookup"><span data-stu-id="0489e-353">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="0489e-354">Cadastro de Pessoa Física (CPF)</span><span class="sxs-lookup"><span data-stu-id="0489e-354">Social Security identifier</span></span> 

<span data-ttu-id="0489e-355">Todos os funcionários devem ter um identificador principal.</span><span class="sxs-lookup"><span data-stu-id="0489e-355">Every employee must have one primary identifier.</span></span> <span data-ttu-id="0489e-356">Esse identificador deve ser o tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="0489e-356">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="0489e-357">No Dayforce, ele é derivado automaticamente como o identificador de pessoa física do funcionário necessário para a contratação.</span><span class="sxs-lookup"><span data-stu-id="0489e-357">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="0489e-358">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-358">Primary (required)</span></span>
- <span data-ttu-id="0489e-359">Tipo de identificação = "CPF"</span><span class="sxs-lookup"><span data-stu-id="0489e-359">Identification Type = "SSN"</span></span>
- <span data-ttu-id="0489e-360">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="0489e-360">Issued Date</span></span>
- <span data-ttu-id="0489e-361">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="0489e-361">Expiration Date</span></span>

<span data-ttu-id="0489e-362">Os funcionários podem declarar vários números de identificação do tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="0489e-362">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="0489e-363">No entanto, somente o registro marcado como **Principal** será integrado ao Dayforce, independentemente de o número estar ativo ou expirado.</span><span class="sxs-lookup"><span data-stu-id="0489e-363">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="0489e-364">Contas bancárias e pagamentos</span><span class="sxs-lookup"><span data-stu-id="0489e-364">Bank accounts and disbursements</span></span>

<span data-ttu-id="0489e-365">Informações de conta bancária válidas devem ser inseridas para qualquer funcionário que opte por ser pago por meio de transferências bancárias.</span><span class="sxs-lookup"><span data-stu-id="0489e-365">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="0489e-366">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-366">Human Resources</span></span>                         | <span data-ttu-id="0489e-367">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-367">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="0489e-368">Número da conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-368">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="0489e-369">Código SWIFT (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-369">SWIFT code (required)</span></span>          | <span data-ttu-id="0489e-370">Campo **ID do banco** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="0489e-370">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="0489e-371">Número da agência (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-371">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="0489e-372">Tipo de conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-372">Bank account type (required)</span></span>   | <span data-ttu-id="0489e-373">Campo **Tipo de conta** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="0489e-373">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="0489e-374">Os valores com suporte incluem **Movimento** e **Folha de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="0489e-374">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="0489e-375">Os funcionários que optarem por serem pagos por meio de transferências bancárias deverão fornecer um link para uma conta de pendência em uma entidade legal que tenha seu endereço principal no México e esteja associada a uma conta bancária válida de um banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="0489e-375">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="0489e-376">Todas as outras contas que não são de pendência são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="0489e-376">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="0489e-377">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="0489e-377">Address information</span></span>

<span data-ttu-id="0489e-378">Todos os funcionários devem ter um local principal.</span><span class="sxs-lookup"><span data-stu-id="0489e-378">Every employee must have one primary location.</span></span> <span data-ttu-id="0489e-379">No Dayforce, esse local é usado para determinar a residência principal do funcionário para fins fiscais.</span><span class="sxs-lookup"><span data-stu-id="0489e-379">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="0489e-380">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-380">Primary (required)</span></span>
- <span data-ttu-id="0489e-381">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-381">Country/region (required)</span></span>
- <span data-ttu-id="0489e-382">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-382">Zip/postal code (required)</span></span>
- <span data-ttu-id="0489e-383">Rua (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-383">Street (required)</span></span>
- <span data-ttu-id="0489e-384">Número da rua (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-384">Street Number (required)</span></span>
- <span data-ttu-id="0489e-385">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="0489e-385">Building Complement</span></span>
- <span data-ttu-id="0489e-386">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-386">City (required)</span></span>
- <span data-ttu-id="0489e-387">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-387">State (required)</span></span>
- <span data-ttu-id="0489e-388">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-388">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="0489e-389">Configurar seus dados para gerar folha de pagamento nos Estados Unidos e no Canadá</span><span class="sxs-lookup"><span data-stu-id="0489e-389">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="0489e-390">Se você está gerando pagamento para funcionários nos Estados Unidos e no Canadá, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="0489e-390">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="0489e-391">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="0489e-391">Departments are required on positions.</span></span>
- <span data-ttu-id="0489e-392">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="0489e-392">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="0489e-393">Você pode configurar o Human Resources para exigir que Posições especifique um Departamento.</span><span class="sxs-lookup"><span data-stu-id="0489e-393">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="0489e-394">Para isso, acesse **Posições Compartilhadas de Recursos Humanos > Posições > Exigir departamentos nas posições**.</span><span class="sxs-lookup"><span data-stu-id="0489e-394">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="0489e-395">Recomendamos que esta configuração seja imposta para a integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-395">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="0489e-396">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="0489e-396">Job types</span></span>

<span data-ttu-id="0489e-397">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="0489e-397">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="0489e-398">Os tipos de trabalho são necessários para processar a folha de pagamento nos Estados Unidos e no Canadá.</span><span class="sxs-lookup"><span data-stu-id="0489e-398">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="0489e-399">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="0489e-399">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="0489e-400">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="0489e-400">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="0489e-401">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="0489e-401">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="0489e-402">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="0489e-402">Job type</span></span>   | <span data-ttu-id="0489e-403">descrição</span><span class="sxs-lookup"><span data-stu-id="0489e-403">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="0489e-404">Por hora</span><span class="sxs-lookup"><span data-stu-id="0489e-404">Hourly</span></span>     | <span data-ttu-id="0489e-405">Por hora</span><span class="sxs-lookup"><span data-stu-id="0489e-405">Hourly</span></span>      |
| <span data-ttu-id="0489e-406">Assalariado</span><span class="sxs-lookup"><span data-stu-id="0489e-406">Salaried</span></span>   | <span data-ttu-id="0489e-407">Assalariado</span><span class="sxs-lookup"><span data-stu-id="0489e-407">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="0489e-408">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="0489e-408">Position types</span></span> 

<span data-ttu-id="0489e-409">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="0489e-409">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="0489e-410">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="0489e-410">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="0489e-411">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="0489e-411">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="0489e-412">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="0489e-412">Position type</span></span>   | <span data-ttu-id="0489e-413">descrição</span><span class="sxs-lookup"><span data-stu-id="0489e-413">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="0489e-414">Horário integral</span><span class="sxs-lookup"><span data-stu-id="0489e-414">Full-time</span></span>       | <span data-ttu-id="0489e-415">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="0489e-415">Full time employee</span></span> |
| <span data-ttu-id="0489e-416">Meio período</span><span class="sxs-lookup"><span data-stu-id="0489e-416">Part-time</span></span>       | <span data-ttu-id="0489e-417">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="0489e-417">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="0489e-418">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="0489e-418">Reason codes</span></span>

<span data-ttu-id="0489e-419">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="0489e-419">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="0489e-420">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="0489e-420">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="0489e-421">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="0489e-421">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="0489e-422">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="0489e-422">Reason code</span></span>    | <span data-ttu-id="0489e-423">descrição</span><span class="sxs-lookup"><span data-stu-id="0489e-423">Description</span></span>      | <span data-ttu-id="0489e-424">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="0489e-424">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="0489e-425">DEMISSÃO</span><span class="sxs-lookup"><span data-stu-id="0489e-425">RESIGNATION</span></span>    | <span data-ttu-id="0489e-426">Demissão</span><span class="sxs-lookup"><span data-stu-id="0489e-426">Resignation</span></span>      | <span data-ttu-id="0489e-427">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-427">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-428">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="0489e-428">TERMINATION</span></span>    | <span data-ttu-id="0489e-429">Finalização</span><span class="sxs-lookup"><span data-stu-id="0489e-429">Termination</span></span>      | <span data-ttu-id="0489e-430">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-430">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-431">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="0489e-431">RETIREMENT</span></span>     | <span data-ttu-id="0489e-432">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="0489e-432">Retirement</span></span>       | <span data-ttu-id="0489e-433">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-433">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-434">OTHER</span><span class="sxs-lookup"><span data-stu-id="0489e-434">OTHER</span></span>          | <span data-ttu-id="0489e-435">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="0489e-435">Other Reasons</span></span>    | <span data-ttu-id="0489e-436">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-436">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-437">DEATH</span><span class="sxs-lookup"><span data-stu-id="0489e-437">DEATH</span></span>          | <span data-ttu-id="0489e-438">Morte</span><span class="sxs-lookup"><span data-stu-id="0489e-438">Death</span></span>            | <span data-ttu-id="0489e-439">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-439">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-440">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="0489e-440">LEAVEOFABSENCE</span></span> | <span data-ttu-id="0489e-441">Licença</span><span class="sxs-lookup"><span data-stu-id="0489e-441">Leave of Absence</span></span> | <span data-ttu-id="0489e-442">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-442">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-443">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="0489e-443">CONTRACTEND</span></span>    | <span data-ttu-id="0489e-444">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="0489e-444">End of Contract</span></span>  | <span data-ttu-id="0489e-445">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-445">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-446">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="0489e-446">SALARYCHANGE</span></span>   | <span data-ttu-id="0489e-447">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="0489e-447">Change of Salary</span></span> | <span data-ttu-id="0489e-448">Remuneração</span><span class="sxs-lookup"><span data-stu-id="0489e-448">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="0489e-449">Estado civil</span><span class="sxs-lookup"><span data-stu-id="0489e-449">Marital status</span></span>

<span data-ttu-id="0489e-450">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-450">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="0489e-451">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-451">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="0489e-452">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-452">Human Resources</span></span>                 | <span data-ttu-id="0489e-453">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-453">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="0489e-454">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-454">Married</span></span>                | <span data-ttu-id="0489e-455">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-455">Married</span></span>              |
| <span data-ttu-id="0489e-456">Único</span><span class="sxs-lookup"><span data-stu-id="0489e-456">Single</span></span>                 | <span data-ttu-id="0489e-457">Único</span><span class="sxs-lookup"><span data-stu-id="0489e-457">Single</span></span>               |
| <span data-ttu-id="0489e-458">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-458">Widowed</span></span>                | <span data-ttu-id="0489e-459">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-459">Widowed</span></span>              |
| <span data-ttu-id="0489e-460">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-460">Divorced</span></span>               | <span data-ttu-id="0489e-461">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-461">Divorced</span></span>             |
| <span data-ttu-id="0489e-462">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="0489e-462">Registered Partnership</span></span> | <span data-ttu-id="0489e-463">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="0489e-463">Domestic Partnership</span></span> |
| <span data-ttu-id="0489e-464">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-464">None</span></span>                   | <span data-ttu-id="0489e-465">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-465">None</span></span>                 |
| <span data-ttu-id="0489e-466">Coabitando</span><span class="sxs-lookup"><span data-stu-id="0489e-466">Cohabiting</span></span>             | <span data-ttu-id="0489e-467">Coabitando</span><span class="sxs-lookup"><span data-stu-id="0489e-467">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="0489e-468">Sexo</span><span class="sxs-lookup"><span data-stu-id="0489e-468">Gender</span></span>

<span data-ttu-id="0489e-469">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-469">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="0489e-470">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-470">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="0489e-471">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-471">Human Resources</span></span>       | <span data-ttu-id="0489e-472">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-472">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="0489e-473">Masculino</span><span class="sxs-lookup"><span data-stu-id="0489e-473">Male</span></span>         | <span data-ttu-id="0489e-474">Masculino</span><span class="sxs-lookup"><span data-stu-id="0489e-474">Male</span></span>            |
| <span data-ttu-id="0489e-475">Feminino</span><span class="sxs-lookup"><span data-stu-id="0489e-475">Female</span></span>       | <span data-ttu-id="0489e-476">Feminino</span><span class="sxs-lookup"><span data-stu-id="0489e-476">Female</span></span>          |
| <span data-ttu-id="0489e-477">Não específico</span><span class="sxs-lookup"><span data-stu-id="0489e-477">Non-specific</span></span> | <span data-ttu-id="0489e-478">*Sem suporte*</span><span class="sxs-lookup"><span data-stu-id="0489e-478">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="0489e-479">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="0489e-479">Earning codes</span></span>

<span data-ttu-id="0489e-480">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="0489e-480">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="0489e-481">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="0489e-481">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="0489e-482">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="0489e-482">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="0489e-483">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="0489e-483">Supported frequencies</span></span>

- <span data-ttu-id="0489e-484">Todas</span><span class="sxs-lookup"><span data-stu-id="0489e-484">All</span></span>
- <span data-ttu-id="0489e-485">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="0489e-485">EVERYPAY</span></span>
- <span data-ttu-id="0489e-486">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="0489e-486">EACHPAYPERIOD</span></span>
- <span data-ttu-id="0489e-487">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="0489e-487">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="0489e-488">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="0489e-488">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="0489e-489">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-489">1OFMTH</span></span>
- <span data-ttu-id="0489e-490">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-490">LASTOFMTH</span></span>
- <span data-ttu-id="0489e-491">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-491">2OFMTH</span></span>
- <span data-ttu-id="0489e-492">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-492">3OFMTH</span></span>
- <span data-ttu-id="0489e-493">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-493">4OFMTH</span></span>
- <span data-ttu-id="0489e-494">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-494">5OFMTH</span></span>
- <span data-ttu-id="0489e-495">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-495">1N2OFMTH</span></span>
- <span data-ttu-id="0489e-496">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-496">3N4OFMTH</span></span>
- <span data-ttu-id="0489e-497">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-497">1N3OFMTH</span></span>
- <span data-ttu-id="0489e-498">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-498">1N4OFMTH</span></span>
- <span data-ttu-id="0489e-499">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-499">2N3OFMTH</span></span>
- <span data-ttu-id="0489e-500">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-500">2N4OFMTH</span></span>
- <span data-ttu-id="0489e-501">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-501">1N2N3OFMTH</span></span>
- <span data-ttu-id="0489e-502">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-502">1N2N4OFMTH</span></span>
- <span data-ttu-id="0489e-503">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-503">1N3N4OFMTH</span></span>
- <span data-ttu-id="0489e-504">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-504">2N3N4OFMTH</span></span>
- <span data-ttu-id="0489e-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="0489e-506">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="0489e-506">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="0489e-507">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="0489e-507">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="0489e-508">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="0489e-508">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="0489e-509">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="0489e-509">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="0489e-510">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="0489e-510">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="0489e-511">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="0489e-511">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="0489e-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="0489e-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="0489e-513">Endereços</span><span class="sxs-lookup"><span data-stu-id="0489e-513">Addresses</span></span>

<span data-ttu-id="0489e-514">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="0489e-514">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="0489e-515">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="0489e-515">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="0489e-516">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-516">Human Resources</span></span>          | <span data-ttu-id="0489e-517">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-517">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="0489e-518">País/Região</span><span class="sxs-lookup"><span data-stu-id="0489e-518">Country/Region</span></span>  | <span data-ttu-id="0489e-519">Código do País</span><span class="sxs-lookup"><span data-stu-id="0489e-519">Country Code</span></span>          |
| <span data-ttu-id="0489e-520">CEP</span><span class="sxs-lookup"><span data-stu-id="0489e-520">Zip/Postal Code</span></span> | <span data-ttu-id="0489e-521">CEP</span><span class="sxs-lookup"><span data-stu-id="0489e-521">Postal Code</span></span>           |
| <span data-ttu-id="0489e-522">Estadual</span><span class="sxs-lookup"><span data-stu-id="0489e-522">State</span></span>           | <span data-ttu-id="0489e-523">Código de estado</span><span class="sxs-lookup"><span data-stu-id="0489e-523">State Code</span></span>            |
| <span data-ttu-id="0489e-524">Cidade</span><span class="sxs-lookup"><span data-stu-id="0489e-524">City</span></span>            | <span data-ttu-id="0489e-525">Cidade</span><span class="sxs-lookup"><span data-stu-id="0489e-525">City</span></span>                  |
| <span data-ttu-id="0489e-526">Região</span><span class="sxs-lookup"><span data-stu-id="0489e-526">County</span></span>          | <span data-ttu-id="0489e-527">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="0489e-527">County (Municipality)</span></span> |
| <span data-ttu-id="0489e-528">Rua</span><span class="sxs-lookup"><span data-stu-id="0489e-528">Street</span></span>          | <span data-ttu-id="0489e-529">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="0489e-529">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="0489e-530">Regiões fiscais</span><span class="sxs-lookup"><span data-stu-id="0489e-530">Tax regions</span></span>

<span data-ttu-id="0489e-531">Regiões fiscais são usadas para determinar os impostos apropriados a serem aplicados durante a geração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="0489e-531">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="0489e-532">As regiões fiscais são mapeadas para o Dayforce como endereços de localização.</span><span class="sxs-lookup"><span data-stu-id="0489e-532">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="0489e-533">A região fiscal padrão deve estar associada à posição ativa do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="0489e-533">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="0489e-534">Região fiscal (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-534">Tax region (required)</span></span>
- <span data-ttu-id="0489e-535">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-535">Country/Region (required)</span></span>
- <span data-ttu-id="0489e-536">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="0489e-536">State (required)</span></span>
- <span data-ttu-id="0489e-537">Região</span><span class="sxs-lookup"><span data-stu-id="0489e-537">County</span></span> 
- <span data-ttu-id="0489e-538">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="0489e-538">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="0489e-539">Configurar seus dados para gerar folha de pagamento no México</span><span class="sxs-lookup"><span data-stu-id="0489e-539">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="0489e-540">Se você está gerando pagamento para funcionários no México, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="0489e-540">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="0489e-541">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="0489e-541">Departments are required on positions.</span></span>
- <span data-ttu-id="0489e-542">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="0489e-542">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="0489e-543">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="0489e-543">Job types</span></span>

<span data-ttu-id="0489e-544">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="0489e-544">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="0489e-545">Tipos de trabalho são necessários para processar a folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="0489e-545">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="0489e-546">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="0489e-546">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="0489e-547">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="0489e-547">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="0489e-548">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="0489e-548">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="0489e-549">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="0489e-549">Job type</span></span>   | <span data-ttu-id="0489e-550">descrição</span><span class="sxs-lookup"><span data-stu-id="0489e-550">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="0489e-551">Por hora</span><span class="sxs-lookup"><span data-stu-id="0489e-551">Hourly</span></span>     | <span data-ttu-id="0489e-552">MX por hora</span><span class="sxs-lookup"><span data-stu-id="0489e-552">MX Hourly</span></span>   |
| <span data-ttu-id="0489e-553">Assalariado</span><span class="sxs-lookup"><span data-stu-id="0489e-553">Salaried</span></span>   | <span data-ttu-id="0489e-554">MX assalariado</span><span class="sxs-lookup"><span data-stu-id="0489e-554">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="0489e-555">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="0489e-555">Position types</span></span> 

<span data-ttu-id="0489e-556">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="0489e-556">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="0489e-557">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="0489e-557">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="0489e-558">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="0489e-558">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="0489e-559">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="0489e-559">Position type</span></span>   | <span data-ttu-id="0489e-560">descrição</span><span class="sxs-lookup"><span data-stu-id="0489e-560">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="0489e-561">Horário integral</span><span class="sxs-lookup"><span data-stu-id="0489e-561">Full-time</span></span>       | <span data-ttu-id="0489e-562">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="0489e-562">Full time employee</span></span> |
| <span data-ttu-id="0489e-563">Meio período</span><span class="sxs-lookup"><span data-stu-id="0489e-563">Part-time</span></span>       | <span data-ttu-id="0489e-564">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="0489e-564">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="0489e-565">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="0489e-565">Reason codes</span></span>

<span data-ttu-id="0489e-566">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="0489e-566">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="0489e-567">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="0489e-567">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="0489e-568">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="0489e-568">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="0489e-569">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="0489e-569">Reason code</span></span>            | <span data-ttu-id="0489e-570">descrição</span><span class="sxs-lookup"><span data-stu-id="0489e-570">Description</span></span>                    | <span data-ttu-id="0489e-571">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="0489e-571">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="0489e-572">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="0489e-572">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="0489e-573">Partida antes da primeira folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="0489e-573">Departure before first payroll</span></span> | <span data-ttu-id="0489e-574">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-574">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-575">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="0489e-575">RESIGNATION</span></span>            | <span data-ttu-id="0489e-576">Demissão</span><span class="sxs-lookup"><span data-stu-id="0489e-576">Resignation</span></span>                    | <span data-ttu-id="0489e-577">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-577">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-578">PENSION</span><span class="sxs-lookup"><span data-stu-id="0489e-578">PENSION</span></span>                | <span data-ttu-id="0489e-579">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="0489e-579">Pension</span></span>                        | <span data-ttu-id="0489e-580">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-580">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-581">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="0489e-581">TERMINATION</span></span>            | <span data-ttu-id="0489e-582">Finalização</span><span class="sxs-lookup"><span data-stu-id="0489e-582">Termination</span></span>                    | <span data-ttu-id="0489e-583">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-583">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-584">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="0489e-584">RETIREMENT</span></span>             | <span data-ttu-id="0489e-585">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="0489e-585">Retirement</span></span>                     | <span data-ttu-id="0489e-586">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-586">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-587">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="0489e-587">ABSENTEE</span></span>               | <span data-ttu-id="0489e-588">Absentista</span><span class="sxs-lookup"><span data-stu-id="0489e-588">Absentee</span></span>                       | <span data-ttu-id="0489e-589">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-589">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-590">OTHER</span><span class="sxs-lookup"><span data-stu-id="0489e-590">OTHER</span></span>                  | <span data-ttu-id="0489e-591">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="0489e-591">Other Reasons</span></span>                  | <span data-ttu-id="0489e-592">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-592">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-593">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="0489e-593">CLOSURE</span></span>                | <span data-ttu-id="0489e-594">Fechamento da empresa</span><span class="sxs-lookup"><span data-stu-id="0489e-594">Business Closure</span></span>               | <span data-ttu-id="0489e-595">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-595">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-596">DEATH</span><span class="sxs-lookup"><span data-stu-id="0489e-596">DEATH</span></span>                  | <span data-ttu-id="0489e-597">Morte</span><span class="sxs-lookup"><span data-stu-id="0489e-597">Death</span></span>                          | <span data-ttu-id="0489e-598">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-598">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-599">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="0489e-599">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="0489e-600">Licença</span><span class="sxs-lookup"><span data-stu-id="0489e-600">Leave of Absence</span></span>               | <span data-ttu-id="0489e-601">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-601">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-602">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="0489e-602">CONTRACTEND</span></span>            | <span data-ttu-id="0489e-603">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="0489e-603">End of Contract</span></span>                | <span data-ttu-id="0489e-604">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="0489e-604">Terminate worker</span></span>     |
| <span data-ttu-id="0489e-605">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="0489e-605">SALARYCHANGE</span></span>           | <span data-ttu-id="0489e-606">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="0489e-606">Change of Salary</span></span>               | <span data-ttu-id="0489e-607">Remuneração</span><span class="sxs-lookup"><span data-stu-id="0489e-607">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="0489e-608">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="0489e-608">Terms of employment</span></span>

<span data-ttu-id="0489e-609">Termos de emprego são usados para criar categorias de termos de emprego.</span><span class="sxs-lookup"><span data-stu-id="0489e-609">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="0489e-610">Os termos são mapeados para o Dayforce como valores de indicador de emprego.</span><span class="sxs-lookup"><span data-stu-id="0489e-610">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="0489e-611">Os termos de emprego e as descrições a seguir são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="0489e-611">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="0489e-612">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="0489e-612">Terms of employment</span></span>   | <span data-ttu-id="0489e-613">descrição</span><span class="sxs-lookup"><span data-stu-id="0489e-613">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="0489e-614">Normal</span><span class="sxs-lookup"><span data-stu-id="0489e-614">Regular</span></span>               | <span data-ttu-id="0489e-615">Normal</span><span class="sxs-lookup"><span data-stu-id="0489e-615">Regular</span></span>     |
| <span data-ttu-id="0489e-616">Direto</span><span class="sxs-lookup"><span data-stu-id="0489e-616">Direct</span></span>                | <span data-ttu-id="0489e-617">Direto</span><span class="sxs-lookup"><span data-stu-id="0489e-617">Direct</span></span>      |
| <span data-ttu-id="0489e-618">Estágio</span><span class="sxs-lookup"><span data-stu-id="0489e-618">Internship</span></span>            | <span data-ttu-id="0489e-619">Estágio</span><span class="sxs-lookup"><span data-stu-id="0489e-619">Internship</span></span>  |
| <span data-ttu-id="0489e-620">Permanente</span><span class="sxs-lookup"><span data-stu-id="0489e-620">Permanent</span></span>             | <span data-ttu-id="0489e-621">Permanente</span><span class="sxs-lookup"><span data-stu-id="0489e-621">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="0489e-622">Estado civil</span><span class="sxs-lookup"><span data-stu-id="0489e-622">Marital status</span></span>

<span data-ttu-id="0489e-623">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-623">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="0489e-624">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-624">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="0489e-625">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-625">Human Resources</span></span>                 | <span data-ttu-id="0489e-626">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-626">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="0489e-627">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-627">Married</span></span>                | <span data-ttu-id="0489e-628">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-628">Married</span></span>                   |
| <span data-ttu-id="0489e-629">Único</span><span class="sxs-lookup"><span data-stu-id="0489e-629">Single</span></span>                 | <span data-ttu-id="0489e-630">Único</span><span class="sxs-lookup"><span data-stu-id="0489e-630">Single</span></span>                    |
| <span data-ttu-id="0489e-631">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-631">Widowed</span></span>                | <span data-ttu-id="0489e-632">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-632">Widowed</span></span>                   |
| <span data-ttu-id="0489e-633">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-633">Divorced</span></span>               | <span data-ttu-id="0489e-634">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-634">Divorced</span></span>                  |
| <span data-ttu-id="0489e-635">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="0489e-635">Registered Partnership</span></span> | <span data-ttu-id="0489e-636">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="0489e-636">Domestic Partnership</span></span>      |
| <span data-ttu-id="0489e-637">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="0489e-637">None</span></span>                   | <span data-ttu-id="0489e-638">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="0489e-638">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="0489e-639">Coabitando</span><span class="sxs-lookup"><span data-stu-id="0489e-639">Cohabiting</span></span>             | <span data-ttu-id="0489e-640">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="0489e-640">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="0489e-641">Sexo</span><span class="sxs-lookup"><span data-stu-id="0489e-641">Gender</span></span>

<span data-ttu-id="0489e-642">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-642">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="0489e-643">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-643">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="0489e-644">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-644">Human Resources</span></span>       | <span data-ttu-id="0489e-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-645">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="0489e-646">Masculino</span><span class="sxs-lookup"><span data-stu-id="0489e-646">Male</span></span>         | <span data-ttu-id="0489e-647">Masculino</span><span class="sxs-lookup"><span data-stu-id="0489e-647">Male</span></span>                      |
| <span data-ttu-id="0489e-648">Feminino</span><span class="sxs-lookup"><span data-stu-id="0489e-648">Female</span></span>       | <span data-ttu-id="0489e-649">Feminino</span><span class="sxs-lookup"><span data-stu-id="0489e-649">Female</span></span>                    |
| <span data-ttu-id="0489e-650">Não específico</span><span class="sxs-lookup"><span data-stu-id="0489e-650">Non-specific</span></span> | <span data-ttu-id="0489e-651">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="0489e-651">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="0489e-652">Forma de pagamento</span><span class="sxs-lookup"><span data-stu-id="0489e-652">Payment method</span></span>

<span data-ttu-id="0489e-653">Os métodos de pagamento dão ao funcionário e à empresa uma maneira de descrever como os funcionários serão pagos.</span><span class="sxs-lookup"><span data-stu-id="0489e-653">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="0489e-654">Os métodos de pagamento são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-654">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="0489e-655">A tabela a seguir mostra como os métodos de pagamento são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-655">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="0489e-656">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-656">Human Resources</span></span>             | <span data-ttu-id="0489e-657">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-657">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="0489e-658">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="0489e-658">Cash</span></span>               | <span data-ttu-id="0489e-659">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="0489e-659">Cash</span></span>                      |
| <span data-ttu-id="0489e-660">Pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="0489e-660">Electronic Payment</span></span> | <span data-ttu-id="0489e-661">Transferir</span><span class="sxs-lookup"><span data-stu-id="0489e-661">Transfer</span></span>                  |
| <span data-ttu-id="0489e-662">Marcar</span><span class="sxs-lookup"><span data-stu-id="0489e-662">Check</span></span>              | <span data-ttu-id="0489e-663">Cheque</span><span class="sxs-lookup"><span data-stu-id="0489e-663">Cheque</span></span>                    |
| <span data-ttu-id="0489e-664">Boleto bancário</span><span class="sxs-lookup"><span data-stu-id="0489e-664">Bank Draft</span></span>         | <span data-ttu-id="0489e-665">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="0489e-665">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="0489e-666">Outros</span><span class="sxs-lookup"><span data-stu-id="0489e-666">Other</span></span>              | <span data-ttu-id="0489e-667">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="0489e-667">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="0489e-668">Tipo de conta bancária</span><span class="sxs-lookup"><span data-stu-id="0489e-668">Bank account type</span></span>

<span data-ttu-id="0489e-669">Os tipos de conta bancária são usados para pagamentos eletrônicos aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="0489e-669">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="0489e-670">Os tipos de conta bancária são mapeados para o Dayforce como informações da conta de transferência.</span><span class="sxs-lookup"><span data-stu-id="0489e-670">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="0489e-671">Os tipos de conta bancária são convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="0489e-671">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="0489e-672">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-672">Human Resources</span></span>            | <span data-ttu-id="0489e-673">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-673">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="0489e-674">Conta corrente</span><span class="sxs-lookup"><span data-stu-id="0489e-674">Checking Account</span></span>  | <span data-ttu-id="0489e-675">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="0489e-675">CheckingAccount</span></span>           |
| <span data-ttu-id="0489e-676">Conta-salário</span><span class="sxs-lookup"><span data-stu-id="0489e-676">Payroll Account</span></span>   | <span data-ttu-id="0489e-677">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="0489e-677">PayrollAccount</span></span>            |
| <span data-ttu-id="0489e-678">Conta de poupança</span><span class="sxs-lookup"><span data-stu-id="0489e-678">Savings Account</span></span>   | <span data-ttu-id="0489e-679">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="0489e-679">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="0489e-680">Conta BankGirot</span><span class="sxs-lookup"><span data-stu-id="0489e-680">BankGirot account</span></span> | <span data-ttu-id="0489e-681">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="0489e-681">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="0489e-682">Conta PlusGirot</span><span class="sxs-lookup"><span data-stu-id="0489e-682">PlusGirot account</span></span> | <span data-ttu-id="0489e-683">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="0489e-683">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="0489e-684">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="0489e-684">Earning codes</span></span>

<span data-ttu-id="0489e-685">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="0489e-685">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="0489e-686">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="0489e-686">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="0489e-687">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="0489e-687">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="0489e-688">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="0489e-688">Supported frequencies</span></span>

- <span data-ttu-id="0489e-689">Todas</span><span class="sxs-lookup"><span data-stu-id="0489e-689">All</span></span>
- <span data-ttu-id="0489e-690">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="0489e-690">EVERYPAY</span></span>
- <span data-ttu-id="0489e-691">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="0489e-691">EACHPAYPERIOD</span></span>
- <span data-ttu-id="0489e-692">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="0489e-692">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="0489e-693">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="0489e-693">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="0489e-694">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-694">1OFMTH</span></span>
- <span data-ttu-id="0489e-695">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-695">LASTOFMTH</span></span>
- <span data-ttu-id="0489e-696">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-696">2OFMTH</span></span>
- <span data-ttu-id="0489e-697">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-697">3OFMTH</span></span>
- <span data-ttu-id="0489e-698">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-698">4OFMTH</span></span>
- <span data-ttu-id="0489e-699">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-699">5OFMTH</span></span>
- <span data-ttu-id="0489e-700">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-700">1N2OFMTH</span></span>
- <span data-ttu-id="0489e-701">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-701">3N4OFMTH</span></span>
- <span data-ttu-id="0489e-702">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-702">1N3OFMTH</span></span>
- <span data-ttu-id="0489e-703">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-703">1N4OFMTH</span></span>
- <span data-ttu-id="0489e-704">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-704">2N3OFMTH</span></span>
- <span data-ttu-id="0489e-705">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-705">2N4OFMTH</span></span>
- <span data-ttu-id="0489e-706">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-706">1N2N3OFMTH</span></span>
- <span data-ttu-id="0489e-707">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-707">1N2N4OFMTH</span></span>
- <span data-ttu-id="0489e-708">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-708">1N3N4OFMTH</span></span>
- <span data-ttu-id="0489e-709">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-709">2N3N4OFMTH</span></span>
- <span data-ttu-id="0489e-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="0489e-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="0489e-711">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="0489e-711">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="0489e-712">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="0489e-712">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="0489e-713">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="0489e-713">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="0489e-714">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="0489e-714">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="0489e-715">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="0489e-715">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="0489e-716">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="0489e-716">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="0489e-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="0489e-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="0489e-718">Endereços</span><span class="sxs-lookup"><span data-stu-id="0489e-718">Addresses</span></span>

<span data-ttu-id="0489e-719">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="0489e-719">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="0489e-720">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="0489e-720">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="0489e-721">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="0489e-721">Human Resources</span></span>              | <span data-ttu-id="0489e-722">Dayforce</span><span class="sxs-lookup"><span data-stu-id="0489e-722">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="0489e-723">País/Região</span><span class="sxs-lookup"><span data-stu-id="0489e-723">Country/Region</span></span>      | <span data-ttu-id="0489e-724">Código do País</span><span class="sxs-lookup"><span data-stu-id="0489e-724">Country Code</span></span>          |
| <span data-ttu-id="0489e-725">CEP</span><span class="sxs-lookup"><span data-stu-id="0489e-725">Zip/Postal Code</span></span>     | <span data-ttu-id="0489e-726">CEP</span><span class="sxs-lookup"><span data-stu-id="0489e-726">Postal Code</span></span>           |
| <span data-ttu-id="0489e-727">Estadual</span><span class="sxs-lookup"><span data-stu-id="0489e-727">State</span></span>               | <span data-ttu-id="0489e-728">Código de estado</span><span class="sxs-lookup"><span data-stu-id="0489e-728">State Code</span></span>            |
| <span data-ttu-id="0489e-729">Cidade</span><span class="sxs-lookup"><span data-stu-id="0489e-729">City</span></span>                | <span data-ttu-id="0489e-730">Cidade</span><span class="sxs-lookup"><span data-stu-id="0489e-730">City</span></span>                  |
| <span data-ttu-id="0489e-731">Região</span><span class="sxs-lookup"><span data-stu-id="0489e-731">County</span></span>              | <span data-ttu-id="0489e-732">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="0489e-732">County (Municipality)</span></span> |
| <span data-ttu-id="0489e-733">Rua</span><span class="sxs-lookup"><span data-stu-id="0489e-733">Street</span></span>              | <span data-ttu-id="0489e-734">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="0489e-734">Address Line 1</span></span>        |
| <span data-ttu-id="0489e-735">Número</span><span class="sxs-lookup"><span data-stu-id="0489e-735">Street Number</span></span>       | <span data-ttu-id="0489e-736">Linha de endereço 2</span><span class="sxs-lookup"><span data-stu-id="0489e-736">Address Line 2</span></span>        |
| <span data-ttu-id="0489e-737">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="0489e-737">Building Complement</span></span> | <span data-ttu-id="0489e-738">Linha de endereço 5</span><span class="sxs-lookup"><span data-stu-id="0489e-738">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="0489e-739">Número do passaporte</span><span class="sxs-lookup"><span data-stu-id="0489e-739">Passport number</span></span>

<span data-ttu-id="0489e-740">Os funcionários podem declarar as informações do passaporte.</span><span class="sxs-lookup"><span data-stu-id="0489e-740">Employees can declare passport information.</span></span> <span data-ttu-id="0489e-741">Essas informações são do tipo de identificação **Passaporte** e estão integradas ao Dayforce como parte das informações específicas do México de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="0489e-741">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="0489e-742">Tipo de identificação = "Passaporte"</span><span class="sxs-lookup"><span data-stu-id="0489e-742">Identification Type = "Passport"</span></span>
- <span data-ttu-id="0489e-743">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="0489e-743">Issued Date</span></span>
- <span data-ttu-id="0489e-744">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="0489e-744">Expiration Date</span></span>

<span data-ttu-id="0489e-745">Os funcionários podem declarar vários números de identificação do tipo de identificação **Passaporte**.</span><span class="sxs-lookup"><span data-stu-id="0489e-745">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="0489e-746">No entanto, apenas a entrada atual do passaporte ativo é integrada ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-746">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="0489e-747">Se todas as entradas do passaporte expirarem, o passaporte emitido mais recentemente será integrado ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="0489e-747">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>

