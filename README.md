# Inventory On Hand By Location Entity Project

This repository contains the code and resources for the **Inventory On Hand By Location Entity** project. The project simply expose the custom Inventory On Hand By Location Entity in Dynamics 365 Finance and Operations.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Managing inventory across multiple locations can be a complex task, especially when it lacks the access to get inventory on hand information. The Inventory On Hand By Location Entity project aims to simplify this process by providing a custom Inventory On Hand By Location Entity that allow user to get inventory by specific location in Dynamics 365 Finance and Operations.

## Features

- **Inventory On Hand Management**: User after built and synced the project can access the InventOnHand data in Dynamics 365 Finance and Operations using Odata

## Installation

To install and set up the Inventory On Hand By Location Entity project, follow these steps:

1. Clone the repository:

   ```shell
   git clone https://github.com/HieuJR/InventoryOnHandByLocationEntityProject.git
   ```

2. Configure the project:

   - Open the project by using visual studio
   - Remember to run it as Administrator

4. Build the project:

   - Right click on this project and click build
   ![build_project](https://github.com/HieuJR/InventoryOnHandByLocationEntityProject/assets/105049467/e98cee3f-0cd6-4d26-b754-055c141c267b)

5. Sync the project:

   - Right click on this project and click synchronize InventoryOnHandByLocationEntityProject ...
   ![sync_project](https://github.com/HieuJR/InventoryOnHandByLocationEntityProject/assets/105049467/5c59a927-4aa1-489d-b3c1-b5338df690de)


## Usage

Once the project is built and synced, you can use the following steps to get started:

1. Make sure you have an access_token to access these APIs below
  ![Postman_oOahWkOvKl](https://github.com/HieuJR/InventoryOnHandByLocationEntityProject/assets/105049467/e3f36d04-8b63-47fe-85aa-5ad796d50a70)

2. Test if an entity have been exposed in Dynamics 365 Finance and Opeations.
  ![text_data_entity](https://github.com/HieuJR/InventoryOnHandByLocationEntityProject/assets/105049467/18b37153-5369-44bd-9e00-bcac3f4b6916)

3. Test if an entity have data or not.
  ![Postman_0Mw4o6KkBR](https://github.com/HieuJR/InventoryOnHandByLocationEntityProject/assets/105049467/d6fed7c8-0514-4d68-848e-2db796122bc7)

## Contributing

Contributions to the Inventory On Hand By Location Entity project are welcome! If you would like to contribute, please follow these steps:

1. Fork the repository on GitHub.

2. Create a new branch with a descriptive name for your feature or bug fix.

3. Implement your changes, adhering to the project's coding guidelines and best practices.

4. Commit and push your changes to your forked repository.

5. Submit a pull request, explaining the purpose and details of your contribution.

6. Wait for feedback and address any requested changes or questions.

Please note that all contributions are subject to review and acceptance by the project maintainers.

## License

Feel free to modify and distribute the codebase as per the terms of this license. Please contact trung.hieu@beehexa.com if you have a questions
