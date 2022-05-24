# Exercícios TypeScript


## Semana 1
### 1: Estamos começando uma pequena comunidade de usuários. Por motivos de desempenho, decidimos armazenar todos os usuários diretamente no código. Dessa forma, podemos fornecer aos nossos desenvolvedores mais oportunidades de interação com o usuário. 
### Todos os problemas relacionados ao Regulamento Geral sobre a Proteção de Dados serão resolvidos algum outro dia. Esta seria a base para nossos futuros experimentos durante esses exercícios. Dados os dados, defina a interface "User" e use-a de acordo.

```bash
export type User = unknown;

export const users: unknown[] = [
    {
        name: 'Wilker',
        age: 25,
        occupation: 'Backend developer'
    },
    {
        name: 'Bob',
        age: 23,
        occupation: 'Product Manager'
    }
];

export function logPerson(user: unknown) {
    console.log(` - ${user.name}, ${user.age}`);
}

console.log('Users:');
users.forEach(logPerson);
```

### 2: Vamos adicionar alguns administradores. Inicialmente, tínhamos apenas usuários no banco de dados na memória.

### Depois de apresentar os Admins (que possuem a propriedade role), precisamos corrigir os tipos para que tudo funcione bem em conjunto. O tipo "Person" está ausente, por favor, defina-o e use-o na array persons e na função logPerson para corrigir todos os erros.

```bash
interface User {

}

interface Admin {

}

export type Person = unknown;

export const persons: User[] /* <- Person[] */ = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Jane Doe',
        age: 32,
        role: 'Administrator'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    },
    {
        name: 'Bruce Willis',
        age: 64,
        role: 'World saver'
    }
];

export function logPerson(user: User) {
    console.log(` - ${user.name}, ${user.age}`);
}

persons.forEach(logPerson);
```

### 3: Como já temos algumas das informações adicionais sobre nossos usuários, é uma boa ideia produzi-las de uma maneira agradável.
### Corrija os erros de tipo na função logPerson. A função logPerson deve aceitar tanto User quanto Admin, ela também deve gerar informações relevantes de acordo com a occupation para User e a role para o Admin.
```bash
interface User {

}

interface Admin {
 
}

export type Person = unknown;

export const persons: Person[] = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Jane Doe',
        age: 32,
        role: 'Administrator'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    },
    {
        name: 'Bruce Willis',
        age: 64,
        role: 'World saver'
    }
];

export function logPerson(person: Person) {
    let additionalInformation: string;
    if (person.role) {
        additionalInformation = person.role;
    } else {
        additionalInformation = person.occupation;
    }
    console.log(` - ${person.name}, ${person.age}, ${additionalInformation}`);
}

persons.forEach(logPerson);
```