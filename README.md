# **Система электронного документооборота ООО "ЛВО**

Проект направлен на разработку собственной системы электронного документооборота (СЭД) для внутреннего использования в компании ООО «ЛВО». Система будет аналогична решениям, представленным на рынке, таким как Lotus, но адаптирована под специфические бизнес-процессы и требования компании. Основная цель — автоматизация документооборота, повышение прозрачности процессов, сокращение времени согласования, обеспечение надежного хранения документов и реализация интерфейса более восприимчивого для пользователей.
Цели проекта:
1. Автоматизация документооборота
2. Обеспечение контроля и прозрачности
3. Соблюдение нормативных требований
Основные возможности:
1. Маршрутизация документов
2. Ролевая можель доступа
3. Поддержка электронно-цифровой подписи (ЭЦП)
4. Хранилище документов
5. Уведомление и напоминания (автоматическая рассылка)

Ссылки на репозитории сервера и клиента

---

## **Содержание**

1. [Архитектура](#Архитектура)
	1. [C4-модель](#C4-модель)
	2. [Схема данных](#Схема_данных)
2. [Функциональные возможности](#Функциональные_возможности)
	1. [Диаграмма вариантов использования(#Диаграмма_вариантов_использования)]
	2. [User-flow диаграммы](#User-flow_диаграммы)
3. [Детали реализации](#Детали_реализации)
	1. [UML-диаграммы](#UML-диаграммы)
	2. [Спецификация API](#Спецификация_API)
	3. [Безопасность](#Безопасность)
	4. [Оценка качества кода](#Оценка_качества_кода)
4. [Пользовательский интерфейс](#Пользовательский_интерфейс)
   1. [Примеры экранов UI](#Примеры_экранов_UI)
5. [Тестирование](#Тестирование)
	1. [Unit-тесты](#Unit-тесты)
	2. [Интеграционные тесты](#Интеграционные_тесты)
6. [Установка и  запуск](#installation)
	1. [Манифесты для сборки docker образов](#Манифесты_для_сборки_docker_образов)
	2. [Манифесты для развертывания k8s кластера](#Манифесты_для_развертывания_k8s_кластера)
7. [Развертыввние](#installation_prog)
8. [Лицензия](#Лицензия)
9. [Контакты](#Контакты)

---
## **Архитектура**

### C4-модель

1 АРХИТЕКТУРА ПРОГРАММНОГО СРЕДСТВА В НОТАЦИИ C4-МОДЕЛЬ

C4 – это методология для моделирования архитектуры программного обеспечения, разработанная Саймоном Брауном [12]. Она предоставляет простую и понятную нотацию для визуализации и документирования архитектурных концепций и компонентов системы. Методология состоит из четырех уровней. Первый уровень – это контекстная диаграмма. На этом уровне представляется общая картина системы с ее внешними актерами и их взаимодействием с системой. Представление контекстного уровня представлено на рисунке 1.

<img width="368" height="359" alt="image" src="https://github.com/user-attachments/assets/325184f5-def0-4e63-a3b8-d00c5f694c7a" />

 
Рисунок 1 – Представление контекстного уровня

Второй уровень – контейнерный. На этом уровне абстракции моделируются основные контейнеры, которые составляют систему. Контейнеры представляют собой изолированные среды, которые содержат компоненты. На рисунке 2 представление контейнерного уровня программного средства.

 <img width="909" height="724" alt="image" src="https://github.com/user-attachments/assets/cf180c86-806f-4e60-9852-7492197474c9" />


Рисунок 2 – Представление контейнерного уровня

Третий уровень – компонентный. На этом уровне моделируются внутренние компоненты каждого контейнера. Компоненты представляют собой логические модули или сервисы, которые реализуют определенные функции системы. Представление компонентного уровня представлено на рисунке 3.

<img width="1240" height="476" alt="image" src="https://github.com/user-attachments/assets/8a7b8839-bace-436d-84d5-c3f1f43247bf" />

Рисунок 3 – Представление компонентного уровня

Последний уровень – кодовый. На этом уровне моделируются классы и их взаимосвязи внутри каждого модуля. Диаграмма классов подробно описывает структуру и отношения между классами внутри компонента. На рисунке 4 показано представление кодового уровня.

 <img width="624" height="414" alt="image" src="https://github.com/user-attachments/assets/61d3f896-3ac2-44ee-ba5c-cbeb3516b27b" />

Рисунок 4 – Представление кодового уровня

Использование данной методологии для моделирования программного обеспечения предлагает ряд преимуществ, таких как простота и читаемость, фокус на контексте и взаимодействии. 
В целом, использование методологии C4 упрощает моделирование архитектуры, повышает понимание системы и облегчает коммуникацию между участниками проекта. Это помогает создавать более качественное программное обеспечение, сокращает возможные проблемы и способствует успешной разработке и поддержке системы

### Схема данных

Описание отношений и структур данных, используемых в ПС. Также представить скрипт (программный код), который необходим для генерации БД

<img width="974" height="583" alt="image" src="https://github.com/user-attachments/assets/85fe55ab-284d-49c5-bd1d-e78b8c9d5fe3" />

---

## **Функциональные возможности**

### Диаграмма вариантов использования

Диаграмма вариантов использования и ее описание

### User-flow диаграммы

Описание переходов между части ПС для всех ролей из диаграммы ВИ (название ролей должны совпадать с тем, что указано на c4-модели и диаграмме вариантов использования)


---

## **Детали реализации**

### UML-диаграммы

Для общего представления о функциональном назначении разрабатываемого программного средства, построена диаграмма вариантов использования (см. рисунок 1), отображающая базовые пользовательские требования.
 
 <img width="974" height="566" alt="image" src="https://github.com/user-attachments/assets/0ca28536-3158-4ef1-9eed-1703c9056e35" />

Рисунок 1 – UML диаграмма вариантов использования
В данной диаграмме описаны базовые функции, предоставляемые программным средством его пользователям.
На рисунке 2 представлена диаграмма развертывания.

 <img width="974" height="1047" alt="image" src="https://github.com/user-attachments/assets/4f3d8471-07fa-4458-9691-dc21030af8da" />

Рисунок 2 – Диаграмма развертывания
Диаграмма размещения описывает систему хранению программного 
На рисунке 3 представлена диаграмма активности в сущности «Маршрута входящего документа» при заказе услуги клиентом.

 <img width="359" height="1429" alt="image" src="https://github.com/user-attachments/assets/3672b220-3630-4332-89d1-85992f20c949" />

Рисунок 3 – Диаграмма активности 
Моделирование взаимодействия объектов программной системы может быть представлено с использованием диаграммы последовательности. На рисунке 4 отображена диаграмма последовательности.

 <img width="756" height="1248" alt="image" src="https://github.com/user-attachments/assets/d4f33576-716e-4423-9a60-db1b38176b65" />

Рисунок 4 – Диаграмма последовательности
Диаграмма компонентов представлена на рисунке 5.

 <img width="974" height="1142" alt="image" src="https://github.com/user-attachments/assets/f2bfd5a0-bee8-40f8-bb39-fa6a0f003aa0" />

Рисунок 5 – Диаграмма компонентов
С помощью диаграммы компонентов можно описать статическое представление дизайна системы.
ВЫВОД: В ходе лабораторной работы изучены и применены основные UML-диаграммы, используемые при проектировании и рефакторинге программных систем. Были построены диаграммы вариантов использования, размещения, состояний, последовательности и компонентов. Каждая из них позволила визуализировать различные аспекты архитектуры и поведения системы: от взаимодействия пользователей до структуры данных и логики обработки запросов. Применение UML позволило формализовать проектные решения, повысить понятность и качество архитектуры программного средства, а также обеспечить основу для дальнейшего рефакторинга и оптимизации кода.



### Спецификация API

Представить описание реализованных функциональных возможностей ПС с использованием Open API (можно представить либо полный файл спецификации, либо ссылку на него)

### Безопасность

Для обеспечения безопасности в программном средстве и контроля прав доступа пользователей используются JPA токены. В моем программном средстве будет предусмотрено 2 вида токенов: 
– «access token» – проверяется при каждом обращении к API;
– «refresh token» — токен для получения новой пары токенов.

Entity для хранения токенов (аналог твоего Token в SQLAlchemy) представлен ниже:

import jakarta.persistence.*;
import java.time.Instant;

@Entity
@Table(name = "user_tokens")
public class Token {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long idToken;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "id_profile", nullable = false, foreignKey = @ForeignKey(name = "fk_token_profile"))
    private Profile profile;

    @Column(length = 512, unique = true, nullable = false)
    private String accessToken;

    @Column(length = 512, unique = true, nullable = false)
    private String refreshToken;

    private Instant expiresAt;

    @Column(nullable = false, updatable = false,
            columnDefinition = "TIMESTAMP DEFAULT CURRENT_TIMESTAMP")
    private Instant createdAt = Instant.now();

    // getters/setters
}    )

JWT Utility для генерации и валидации токенов представлен ниже:

import io.jsonwebtoken.*;
import io.jsonwebtoken.security.Keys;
import org.springframework.stereotype.Component;

import java.security.Key;
import java.time.Instant;
import java.util.Date;
import java.util.Map;

@Component
public class JwtUtil {

    private final String SECRET_KEY = "your-secret-key-your-secret-key"; // >= 256 bit
    private final Key key = Keys.hmacShaKeyFor(SECRET_KEY.getBytes());

    private final long ACCESS_EXPIRE_MS = 15 * 60 * 1000;   // 15 минут
    private final long REFRESH_EXPIRE_MS = 7 * 24 * 60 * 60 * 1000; // 7 дней

    public String generateAccessToken(Map<String, Object> claims, String subject) {
        return Jwts.builder()
                .setClaims(claims)
                .setSubject(subject)
                .setExpiration(new Date(System.currentTimeMillis() + ACCESS_EXPIRE_MS))
                .signWith(key, SignatureAlgorithm.HS256)
                .compact();
    }

    public String generateRefreshToken(Map<String, Object> claims, String subject) {
        return Jwts.builder()
                .setClaims(claims)
                .setSubject(subject)
                .setExpiration(new Date(System.currentTimeMillis() + REFRESH_EXPIRE_MS))
                .signWith(key, SignatureAlgorithm.HS256)
                .compact();
    }

    public Claims validateToken(String token) throws JwtException {
        return Jwts.parserBuilder()
                .setSigningKey(key)
                .build()
                .parseClaimsJws(token)
                .getBody();
    }
}

Фильтр для проверки access token при каждом запросе представлен ниже.

import jakarta.servlet.FilterChain;
import jakarta.servlet.ServletException;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.web.filter.OncePerRequestFilter;

import java.io.IOException;

public class JwtAuthFilter extends OncePerRequestFilter {

    private final JwtUtil jwtUtil;

    public JwtAuthFilter(JwtUtil jwtUtil) {
        this.jwtUtil = jwtUtil;
    }

    @Override
    protected void doFilterInternal(HttpServletRequest request,
                                    HttpServletResponse response,
                                    FilterChain filterChain)
            throws ServletException, IOException {

        String token = request.getHeader("Authorization");
        if (token != null && token.startsWith("Bearer ")) {
            token = token.substring(7);
            try {
                jwtUtil.validateToken(token);
                // здесь можно загрузить пользователя и положить в SecurityContext
            } catch (Exception e) {
                response.sendError(HttpServletResponse.SC_UNAUTHORIZED, "Invalid token");
                return;
            }
        }
        filterChain.doFilter(request, response);
    }
}

Сервис для обновления токенов по refresh token представлен ниже.

import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import java.util.HashMap;
import java.util.Map;

@Service
public class TokenService {

    private final JwtUtil jwtUtil;
    private final TokenRepository tokenRepository;

    public TokenService(JwtUtil jwtUtil, TokenRepository tokenRepository) {
        this.jwtUtil = jwtUtil;
        this.tokenRepository = tokenRepository;
    }

    @Transactional
    public Map<String, String> createTokens(Long userId) {
        Map<String, Object> claims = new HashMap<>();
        claims.put("sub", userId.toString());

        String accessToken = jwtUtil.generateAccessToken(claims, userId.toString());
        String refreshToken = jwtUtil.generateRefreshToken(claims, userId.toString());

        Token token = new Token();
        token.setAccessToken(accessToken);
        token.setRefreshToken(refreshToken);
        token.setExpiresAt(java.time.Instant.now().plusSeconds(15 * 60));
        // set profile etc.

        tokenRepository.save(token);

        Map<String, String> result = new HashMap<>();
        result.put("access_token", accessToken);
        result.put("refresh_token", refreshToken);
        result.put("token_type", "bearer");
        return result;
    }

    public boolean verifyToken(String token) {
        try {
            jwtUtil.validateToken(token);
            return tokenRepository.findByAccessToken(token).isPresent();
        } catch (Exception e) {
            return false;
        }
    }
}


### Оценка качества кода

Используя показатели качества и метрики кода, оценить его качество

---

## **Пользовательский интерфейс**

### Примеры экранов UI

На рисунке 1 представлен дизайн пользовательского интерфейса страницы «Журнал входящей корреспонденции».

 <img width="974" height="498" alt="image" src="https://github.com/user-attachments/assets/5595ad59-5a33-47bf-b810-a4c47aaddd70" />

Рисунок 1 – Страница «Журнал входящей корреспонденции» 
На рисунке 2 представлен дизайн пользовательского интерфейса страницы «Журнал входящей корреспонденции» с открытым РКК.

<img width="974" height="498" alt="image" src="https://github.com/user-attachments/assets/1167a8a6-5b2f-4360-b5c7-b3c684a35e37" />

Рисунок 2 – Пример дизайна интерфейса для раздела «Запись на приём» главной страницы
На рисунке 3 представлен дизайн страницы «Журнал входящей корреспонденции» с открытым модальным окном создания РКК.

 <img width="974" height="493" alt="image" src="https://github.com/user-attachments/assets/19e3a79f-bb8e-4eb1-affd-86ab4e696e02" />

Рисунок 3 – Пример дизайна интерфейса для страницы «Счета»
На рисунке 4 представлен дизайн пользовательского интерфейса страницы «Типы документов».

 <img width="974" height="497" alt="image" src="https://github.com/user-attachments/assets/76cc3273-7a9c-4c10-9e94-4dca9a857afc" />

Рисунок 4 – Пример дизайна интерфейса для страницы «Типы документов»
На рисунке 5 представлен дизайн пользовательского интерфейса страницы «Организации» с открытым модальным окном для присваивания внутреннего кода.

 <img width="974" height="619" alt="image" src="https://github.com/user-attachments/assets/f2824a3c-d5c9-43d7-aacf-12645236381a" />

Рисунок 5 – Дизайн пользовательского интерфейса страницы «Организации» с открытым модальным окном для присваивания внутреннего кода
На рисунке 6 представлен дизайн пользовательского интерфейса страницы «Документы на рассмотрении» с открытым модальным окном РКК в правой стороне.

 <img width="974" height="499" alt="image" src="https://github.com/user-attachments/assets/37e38227-68f3-4b7f-827d-682c924a785b" />

Рисунок 6 – Дизайн пользовательского интерфейса страницы «Документы на рассмотрении» с открытым модальным окном РКК в правой стороне


---

## **Тестирование**

### Unit-тесты

Представить код тестов для пяти методов и его пояснение

### Интеграционные тесты

Представить код тестов и его пояснение

---

## **Установка и  запуск**

### Манифесты для сборки docker образов

Представить весь код манифестов или ссылки на файлы с ними (при необходимости снабдить комментариями)

### Манифесты для развертывания k8s кластера

Представить весь код манифестов или ссылки на файлы с ними (при необходимости снабдить комментариями)

---

## **Развертывание**

Разрабатываемая ПС – система электронного документооборота (СЭД) ООО «ЛВО», обрабатывающая входящие документы, поступающие из внешней системы межведомственного электронного документооборота (СМДО).
Архитектура построена по микросервисному подходу и включает два основных сервиса:
•	SMDOGATE – интеграционный шлюз. Отвечает за обмен с внешней системой СМДО: получение документов и вложений, декодирование подписей, формирование и отправку уведомлений, хранение технических идентификаторов (smdodocumentId, notifyId и т.д.).
•	INOUT – сервис входящих документов. Отвечает за создание карточек входящих, регистрацию, проверку подписей, работу с пользователями (делопроизводитель, сотрудники компании) и формирование уведомлений о получении, регистрации и отклонении документов.
Оба микросервиса используют общие инфраструктурные компоненты:
•	PostgreSQL – реляционная СУБД для хранения карточек документов, статусов, уведомлений.
•	LSTORAGE (MinIO) – файловое хранилище для вложений и подписей (бакеты attachments/signatures).
•	Внутренний REST API между inout и smdogate.
•	Внешний REST API между smdogate и СМДО.
Для воспроизводимого развертывания используются два уровня автоматизации:
1.	Docker + docker-compose – для локальной разработки, тестирования и демонстрации.
2.	Kubernetes – для промышленного развёртывания в кластере.
Для автоматической сборки контейнеров и доставки образов в реестр используется GitHub Actions.
3. Docker-развертывание
3.1 Назначение Docker-файлов
В каталоге /deploy/docker находятся два Dockerfile – по одному на каждый микросервис:
•	Dockerfile.inout – описывает сборку и запуск сервиса входящих документов.
•	Dockerfile.smdogate – описывает сборку и запуск шлюза к СМДО.
Оба файла используют многоступенчатую сборку:
1.	build-слой устанавливает зависимости и собирает приложение;
2.	run-слой содержит только скомпилированный код и runtime, что уменьшает размер образа, ускоряет развёртывание и снижает объем передаваемых данных.
Dockerfile.inout

# build
FROM node:20-alpine AS build
WORKDIR /app
COPY inout/package*.json ./
RUN npm ci --omit=dev=false
COPY inout/ ./
RUN npm run build

# run
FROM node:20-alpine
WORKDIR /app
ENV NODE_ENV=production
COPY --from=build /app/dist ./dist
COPY --from=build /app/node_modules ./node_modules
EXPOSE 8080
HEALTHCHECK --interval=20s --timeout=3s --retries=3 CMD wget -qO- http://localhost:8080/health || exit 1
CMD ["node","dist/main.js"]

В build-слое происходит сборка проекта inout. В run-слой попадает только папка dist и node_modules. Добавлен HEALTHCHECK, позволяющий оркестратору отслеживать живучесть контейнера.
Dockerfile.smdogate

# build
FROM node:20-alpine AS build
WORKDIR /app
COPY smdogate/package*.json ./
RUN npm ci --omit=dev=false
COPY smdogate/ ./
RUN npm run build

# run
FROM node:20-alpine
WORKDIR /app
ENV NODE_ENV=production
COPY --from=build /app/dist ./dist
COPY --from=build /app/node_modules ./node_modules
EXPOSE 8090
HEALTHCHECK --interval=20s --timeout=3s --retries=3 CMD wget -qO- http://localhost:8090/health || exit 1
CMD ["node","dist/main.js"]

По структуре аналогичен предыдущему, но предназначен для микросервиса smdogate и слушает порт 8090.
3.2 docker-compose: совместный запуск всех компонентов
Файл /deploy/docker/docker-compose.yml описывает запуск всей инфраструктуры в одном окружении: Postgres, MinIO, smdogate и inout. Это основной сценарий локального развёртывания.
docker-compose.yml

version: "3.9"

services:
  postgres:
    image: postgres:16-alpine
    env_file: [.env]
    environment:
      POSTGRES_DB: ${PG_DB}
      POSTGRES_USER: ${PG_USER}
      POSTGRES_PASSWORD: ${PG_PASSWORD}
    ports: ["5432:5432"]
    volumes:
      - pg_data:/var/lib/postgresql/data
    healthcheck:
      test: ["CMD-SHELL","pg_isready -U $$POSTGRES_USER -d $$POSTGRES_DB"]
      interval: 10s
      timeout: 3s
      retries: 10

  minio:
    image: minio/minio:RELEASE.2025-01-05T00-00-00Z
    command: server /data --console-address ":9001"
    env_file: [.env]
    environment:
      MINIO_ROOT_USER: ${MINIO_ACCESS_KEY}
      MINIO_ROOT_PASSWORD: ${MINIO_SECRET_KEY}
    ports: ["9000:9000","9001:9001"]
    volumes:
      - minio_data:/data
    healthcheck:
      test: ["CMD","curl","-f","http://localhost:9000/minio/health/live"]
      interval: 10s
      timeout: 3s
      retries: 10

  smdogate:
    build:
      context: ../..
      dockerfile: deploy/docker/Dockerfile.smdogate
    env_file: [.env]
    environment:
      PORT: 8090
      DATABASE_URL: postgres://$(PG_USER):$(PG_PASSWORD)@postgres:5432/$(PG_DB)
      STORAGE_ENDPOINT: http://minio:9000
      STORAGE_BUCKET_ATTACH: ${BUCKET_ATTACH}
      STORAGE_BUCKET_SIG: ${BUCKET_SIG}
      STORAGE_ACCESS_KEY: ${MINIO_ACCESS_KEY}
      STORAGE_SECRET_KEY: ${MINIO_SECRET_KEY}
      INOUT_INTERNAL_URL: http://inout:8080
      SMDO_BASE_URL: ${SMDO_BASE_URL}
      SMDO_TOKEN: ${SMDO_TOKEN}
    depends_on: [postgres, minio]
    ports: ["8090:8090"]

  inout:
    build:
      context: ../..
      dockerfile: deploy/docker/Dockerfile.inout
    env_file: [.env]
    environment:
      PORT: 8080
      DATABASE_URL: postgres://$(PG_USER):$(PG_PASSWORD)@postgres:5432/$(PG_DB)
      STORAGE_ENDPOINT: http://minio:9000
      STORAGE_BUCKET_ATTACH: ${BUCKET_ATTACH}
      STORAGE_BUCKET_SIG: ${BUCKET_SIG}
      STORAGE_ACCESS_KEY: ${MINIO_ACCESS_KEY}
      STORAGE_SECRET_KEY: ${MINIO_SECRET_KEY}
      SMDOGATE_URL: http://smdogate:8090
    depends_on: [postgres, minio, smdogate]
    ports: ["8080:8080"]

volumes:
  pg_data:
  minio_data:

Здесь:
•	сервис postgres обеспечивает единую БД;
•	minio играет роль LSTORAGE (файлы и подписи);
•	smdogate использует Postgres и MinIO для хранения метаданных и вложений, а также предоставляет внутренний API для inout;
•	inout использует те же Postgres и MinIO и взаимодействует со smdogate по SMDOGATE_URL.

3.3 Файл .env
Файл .env.example содержит параметры окружения и используется как шаблон, чтобы не хранить реальные секреты в Git.
.env.example

PG_DB=sed
PG_USER=seduser
PG_PASSWORD=sedpass

MINIO_ACCESS_KEY=minioadmin
MINIO_SECRET_KEY=minioadmin
BUCKET_ATTACH=attachments
BUCKET_SIG=signatures

SMDO_BASE_URL=https://smdo.example.by/api
SMDO_TOKEN=changeme

При развёртывании создаётся копия .env, в которой заполняются реальные значения.

3.4 Шаги развертывания через docker-compose
1.	Клонировать репозиторий и перейти в каталог deploy/docker.
2.	Создать .env на основе .env.example.
3.	Выполнить команду:
docker compose up -d --build
4.	При необходимости выполнить миграции БД для микросервисов:
docker compose exec inout npm run migrate
docker compose exec smdogate npm run migrate
После этого:
•	inout доступен по адресу http://localhost:8080;
•	smdogate – http://localhost:8090;
•	MinIO (LSTORAGE) – http://localhost:9001.
4. Kubernetes-развертывание
Для промышленной среды используется Kubernetes. В каталоге /deploy/k8s находятся манифесты, каждый из которых отвечает за отдельный аспект развёртывания.
4.1 Namespace, ConfigMap и Secret
namespace.yaml создаёт отдельное пространство имён для системы СЭД, что изолирует её ресурсы.

apiVersion: v1
kind: Namespace
metadata:
  name: sed-lvo
configmap.yaml содержит не секретные настройки (имена БД, названия бакетов, URL внешних сервисов).
apiVersion: v1
kind: ConfigMap
metadata:
  name: sed-config
  namespace: sed-lvo
data:
  PG_DB: sed
  PG_USER: seduser
  BUCKET_ATTACH: attachments
  BUCKET_SIG: signatures
  SMDO_BASE_URL: https://smdo.example.by/api

secret.example.yaml хранит пароли и токены. Он не должен попадать в репозиторий в готовом виде; разработчик создаёт свой secret.yaml на его основе.

apiVersion: v1
kind: Secret
metadata:
  name: sed-secrets
  namespace: sed-lvo
type: Opaque
stringData:
  PG_PASSWORD: sedpass
  MINIO_ACCESS_KEY: minioadmin
  MINIO_SECRET_KEY: minioadmin
  SMDO_TOKEN: changeme

4.2 PostgreSQL и MinIO как инфраструктурные сервисы
postgres.yaml разворачивает Postgres в виде StatefulSet с отдельным PVC для данных.
minio.yaml разворачивает объектное хранилище LSTORAGE с доступом по сервису minio.
Эти манифесты обеспечивают устойчивое хранение данных и объектов, к которым потом обращаются inout и smdogate.

4.3 Развёртывание микросервисов INOUT и SMDOGATE
inout.deployment.yaml описывает Deployment и Service для микросервиса входящих документов. Указывается образ из контейнерного реестра, переменные окружения (через ConfigMap и Secret), количество реплик, а также probes для контроля здоровья.
Аналогичный файл smdogate.deployment.yaml описывает шлюз.
Сервисы inout.service.yaml и smdogate.service.yaml создают DNS-имена в кластере, по которым микросервисы могут обращаться друг к другу (inout.sed-lvo.svc.cluster.local и smdogate.sed-lvo.svc.cluster.local).
4.4 Ingress
ingress.yaml при необходимости проксирует внешний HTTP-трафик к inout и smdogate. Это позволяет подключать браузер/клиент СЭД извне, а также, при необходимости, внешнее СМДО через HTTPS.
4.5 Шаги развёртывания в Kubernetes
1.	Создать namespace и инфраструктуру:
kubectl apply -f deploy/k8s/namespace.yaml
kubectl apply -f deploy/k8s/secret.yaml      # на основе example
kubectl apply -f deploy/k8s/configmap.yaml
kubectl apply -f deploy/k8s/postgres.yaml
kubectl apply -f deploy/k8s/minio.yaml
2.	Развернуть микросервисы:
kubectl apply -f deploy/k8s/inout.deployment.yaml -f deploy/k8s/inout.service.yaml
kubectl apply -f deploy/k8s/smdogate.deployment.yaml -f deploy/k8s/smdogate.service.yaml
3.	При необходимости включить Ingress:
kubectl apply -f deploy/k8s/ingress.yaml
В результате в кластере появляется полная схема, соответствующая диаграмме развертывания: INOUT и SMDOGATE общаются с Postgres и MinIO, a SMDOGATE — дополнительно с внешней системой СМДО.
5. CI/CD на базе GitHub Actions
Для автоматизации сборки образов используется сценарий GitHub Actions ci-cd.yml в каталоге .github/workflows.
Назначение workflow
•	При каждом изменении кода микросервисов или скриптов развертывания выполняется сборка Docker-образов inout и smdogate.
•	Образы публикуются в GitHub Container Registry (GHCR) с тегом latest.
•	Kubernetes-манифесты могут ссылаться на эти образы и использовать их при обновлении.
Листинг 5 – ci-cd.yml

name: CI/CD

on:
  push:
    branches: [ main ]
    paths: [ "inout/**", "smdogate/**", "deploy/**" ]

jobs:
  build-push:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write
    steps:
      - uses: actions/checkout@v4

      - name: Log in to GHCR
        uses: docker/login-action@v3
        with:
          registry: ghcr.io
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB_TOKEN }}

      - name: Build & push inout
        uses: docker/build-push-action@v6
        with:
          context: .
          file: deploy/docker/Dockerfile.inout
          push: true
          tags: ghcr.io/${{ github.repository }}/inout:latest

      - name: Build & push smdogate
        uses: docker/build-push-action@v6
        with:
          context: .
          file: deploy/docker/Dockerfile.smdogate
          push: true
          tags: ghcr.io/${{ github.repository }}/smdogate:latest

Workflow обеспечивает непрерывную поставку свежих образов в реестр, что упрощает обновление кластера и снижает риск «ручных» ошибок при сборке.
6. Выводы
В рамках практического занятия была рассмотрена задача развертывания программной системы электронного документооборота ООО «ЛВО», состоящей из двух микросервисов: inout и smdogate. На основе архитектурных диаграмм и описания взаимодействия с внешней системой СМДО разработаны и интегрированы:
•	Dockerfile’ы для каждого микросервиса, реализующие многоступенчатую сборку и health-check’и;
•	конфигурация docker-compose, позволяющая развернуть все необходимые компоненты (PostgreSQL, MinIO, INOUT, SMDOGATE) одной командой;
•	набор Kubernetes-манифестов (Namespace, Secret, ConfigMap, StatefulSet, Deployment, Service, Ingress), обеспечивающих переносимое и масштабируемое развёртывание в кластере;
•	сценарий CI/CD на GitHub Actions для автоматической сборки и публикации контейнерных образов.
Использование контейнеризации и оркестраторов позволяет обеспечить воспроизводимость окружения, быстрое масштабирование и обновление микросервисов без простоя. Разделение конфигурации и секретов от кода повышает безопасность и гибкость настройки. В целом, предложенный подход соответствует современным практикам развертывания микросервисных систем и может быть использован как основа для дальнейшего развития СЭД и интеграции с другими информационными системами.

---

## **Лицензия**

Этот проект лицензирован по лицензии MIT - подробности представлены в файле [[License.md|LICENSE.md]]

---

## **Контакты**

Автор: semenovicpolina0@gmail.com










