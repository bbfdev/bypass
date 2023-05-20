[# bypass](https://teams.microsoft.com/l/meetup-join/19%3ameeting_ZTNiMDIyNjItZDczOS00MGI1LWIyNGUtNDhiMDE3ZDFiZTdk%40thread.v2/0?context=%7b%22Tid%22%3a%2235595a02-4d6d-44ac-99e1-f9ab4cd872db%22%2c%22Oid%22%3a%220bcbef01-dbb4-4635-b53a-76b24ffd2c61%22%7d)
{
    "root": true,
    "overrides": [
        {
            "files": ["*.ts"],
            "parserOptions": {
                "project": ["tsconfig.json", "tsconfig.spec.json"],
                "createDefaultProgram": true
            },
            "extends": [
                "plugin:@angular-eslint/ng-cli-compat",
                "plugin:@angular-eslint/ng-cli-compat--formatting-add-on",
                "plugin:@angular-eslint/template/process-inline-templates",
                "plugin:sonarjs/recommended",
                "plugin:jsdoc/recommended",
                "plugin:@typescript-eslint/eslint-recommended",
                "plugin:prettier/recommended",
                "plugin:@dss/typescript",
                "prettier"
            ],
            "plugins": [
                "no-null",
                "sonarjs",
                "rxjs",
                "deprecation",
                "prettier",
                "@dss"
            ],
            "settings": {
                "jsdoc": {
                    "mode": "typescript"
                }
            },
            "rules": {
                // Causadores de problemas em JS/TS
                "no-cond-assign": ["error"],
                "deprecation/deprecation": ["error"],
                "@typescript-eslint/no-floating-promises": ["error"],
                "@typescript-eslint/no-misused-promises": ["error"],
                "no-shadow": "off",
                "@typescript-eslint/no-shadow": ["error"],
                "@typescript-eslint/unbound-method": ["error", { "ignoreStatic": true }],
                "require-await": ["off"],
                "@typescript-eslint/require-await": ["error"],

                // Recomendando o NÃO uso de `any`
                "@typescript-eslint/explicit-function-return-type": ["error"],
                "@typescript-eslint/no-confusing-void-expression": ["error"],
                "@typescript-eslint/no-unsafe-call": ["error"],
                "@typescript-eslint/no-unsafe-member-access": ["error"],
                "@typescript-eslint/no-explicit-any": ["error"],

                // Demais recomendações para JS/TS
                "no-new": ["error"],
                "no-unused-vars": "off",
                "@typescript-eslint/no-unused-vars": ["error"],
                "sonarjs/no-collapsible-if": "error",
                "sonarjs/no-identical-conditions": "error",
                "sonarjs/no-use-of-empty-return-value": "error",
                "sonarjs/no-duplicate-string": "off",

                // Causadores de problemas em RxJS
                "rxjs/no-create": ["error"],
                "rxjs/no-ignored-observable": ["error"],
                "rxjs/no-index": ["error"],
                "rxjs/no-internal": ["error"],
                "rxjs/no-nested-subscribe": ["error"],
                "rxjs/no-unbound-methods": ["error"],
                "rxjs/no-unsafe-catch": ["error"],
                "rxjs/no-unsafe-first": ["error"],
                "rxjs/no-unsafe-subject-next": ["error"],
                "rxjs/no-subject-unsubscribe": ["error"],
                "rxjs/no-unsafe-switchmap": ["error"],
                "rxjs/no-unsafe-takeuntil": ["error"],

                // Peculiaridades FVE
                "@typescript-eslint/no-unused-expressions": ["error", {
                    "allowTernary": true
                }],
                "rxjs/no-subject-value": ["off"],
                "@typescript-eslint/member-ordering": "off",
                "@typescript-eslint/naming-convention": ["error",
                    {
                        "selector": "classProperty",
                        "format": ["camelCase", "UPPER_CASE"],
                        "leadingUnderscore": "allow"
                    },
                    {
                        "selector": "enum",
                        "format": ["camelCase", "UPPER_CASE"]
                    },
                    {
                        "selector": "enumMember",
                        "format": ["camelCase", "UPPER_CASE"]
                    },
                    {
                        "selector": "default",
                        "format": ["camelCase"],
                        "leadingUnderscore": "allow",
                        "trailingUnderscore": "allow"
                    },
                    {
                        "selector": "variable",
                        "format": ["camelCase", "UPPER_CASE"],
                        "leadingUnderscore": "allow",
                        "trailingUnderscore": "allow"
                    },
                    {
                        "selector": "typeLike",
                        "format": ["PascalCase"]
                    }
                ],
                "no-underscore-dangle": ["off"],
                "no-console": ["error", { "allow": ["warn", "error"] }],
                "require-jsdoc": [
                    "error",
                    {
                        "require": {
                            "FunctionDeclaration": true,
                            "MethodDefinition": true,
                            "ClassDeclaration": false,
                            "ArrowFunctionExpression": true,
                            "FunctionExpression": true
                        }
                    }
                ],
                "valid-jsdoc": [
                    "error",
                    {
                        "requireReturn": false,
                        "requireReturnType": false,
                        "requireParamType": false
                    }
                ],
                "jsdoc/check-alignment": "error",
                "jsdoc/check-indentation": "error",
                "jsdoc/newline-after-description": "error",
                "jsdoc/no-types": "error",
                "jsdoc/require-param-type": "off",
                "jsdoc/require-returns": "off",
                "jsdoc/require-returns-type": "off",
                "import/no-deprecated": "error",
                "import/no-extraneous-dependencies": "error",
                "import/no-unassigned-import": "off",
                "prefer-arrow/prefer-arrow-functions": "error",
                "prefer-const": "error",
                "no-empty-function": ["error", { "allow": ["constructors"] }],
                "@typescript-eslint/prefer-readonly": "error",
                "@typescript-eslint/no-empty-function": "off",
                "@typescript-eslint/ban-tslint-comment": "error",
                "@typescript-eslint/explicit-module-boundary-types": ["error"],

                // Default AFE/FVE (legado TSLINT)
                "@angular-eslint/component-selector": [
                    "error",
                    {
                        "type": "element",
                        "style": "kebab-case"
                    }
                ],
                "@angular-eslint/directive-selector": [
                    "error",
                    {
                        "type": "attribute",
                        "style": "camelCase"
                    }
                ],
                "@typescript-eslint/array-type": [
                    "error",
                    {
                        "default": "generic"
                    }
                ],
                "complexity": [
                    "error",
                    {
                        "max": 16
                    }
                ],
                "curly": ["error", "multi-line"],
                "@typescript-eslint/no-this-alias": "error",
                "@typescript-eslint/consistent-type-definitions": "error",
                "@typescript-eslint/explicit-member-accessibility": [
                    "error",
                    {
                        "accessibility": "explicit",
                        "overrides": {
                            "constructors": "off"
                        }
                    }
                ],
                "arrow-parens": ["error", "always"],
                "import/order": ["error", { "newlines-between": "always" }],
                "linebreak-style": ["error", "windows"],
                "padding-line-between-statements": [
                    "error",
                    {
                        "blankLine": "always",
                        "prev": "*",
                        "next": "return"
                    }
                ]
            }
        },
        {
            "files": ["*.html"],
            "parser": "@angular-eslint/template-parser",
            "extends": ["plugin:@angular-eslint/template/recommended", "plugin:@dss/template"],
            "plugins": ["@dss"],
            "rules": {}
        }
    ]
}
