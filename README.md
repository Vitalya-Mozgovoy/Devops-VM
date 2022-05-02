# Devops-VM
provider "aws" {
  region  = "us-west-2"
  version = "~> 2.18"
}

resource "aws_cloudwatch_log_group" "lambda" {
  name = "/aws/lambda/netology"

  retention_in_days = 1
}

#!/usr/bin/env bash

STUDENT_NAME="Vitaliy"

echo "my name in ${STUDENT_NAME}"

Заголовок
Подзаголовок

    Текст ссылки
    Второй пункт списка

local k = (import 'ksonnet-util/kausal.libsonnet');

{
  _config:: {
    name: 'change_me',
    namespace: std.extVar('qbec.io/defaultNs'),

    container: {
      requests: { cpu: '10m', memory: '100Mi' },
      limits: { cpu: '200m', memory: '200Mi' },
    },
  },

  local serviceAccount = k.core.v1.serviceAccount,

  serviceAccount:
    serviceAccount.new($._config.name) +
    serviceAccount.mixin.metadata.withNamespace($._config.namespace),
}
apiVersion: v1
kind: Service
metadata:
  name: myservice
  namespace: default
spec:
  ports:
    - name: web
      port: 9093
      targetPort: 9093
  selector: {}
