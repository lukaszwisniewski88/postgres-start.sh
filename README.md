# Local PostgreSQL Docker Manager

This repository contains a Bash script that helps you manage a local instance of PostgreSQL using Docker. The script allows you to start and stop a PostgreSQL container, as well as create and restore pg_dump backups.

## Requirements

To use this script, you need to have the following installed on your system:

- Docker: Make sure Docker is installed and running on your machine.
- OpenSSL: Required for generating passwords for the PostgreSQL database.

## Getting Started

1. Clone the repository to your local machine:

```bash
git clone https://github.com/lukaszwisniewski88/postgres-start.sh
cd postgres-start
```

2. Make the script file executable and copy wherewer you like it
   - it can be in your project dir
   - or in your path, if you want to use it in multiple projects

## Note

- When starting the PostgreSQL container for the first time, the script will automatically generate a new password for the database and save it in the environment file (.env or .env.local) of your project.

- The script will automatically detect and use the name of the current project directory as the database name. It will save the DATABASE_URL in the environment file as follows:

```
DATABASE_URL=postgresql://postgres:your-generated-password@localhost:5432/your-project-name?schema=public
```

## Restoring a Database Backup

- The script automatically creates backups (pg_dump) of the database when stopping the container. These backups are saved in the `pg_dumps` directory within the project.

- To restore the latest pg_dump backup, the script will automatically detect the latest backup file and restore it when you start the PostgreSQL container.

## Contributing

Contributions to this repository are welcome! If you have any improvements or bug fixes to suggest, please feel free to create a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
