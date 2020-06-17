# CLOUDFOUNDRY_SERVICE_INSTANCE_ENV_TEST
자바 어플리케이션의 서비스 인스턴스 바인딩 후 해당 값을 가져오는 예제입니다.


curl {URL}/services : (get)VCAP_SERVICES의 해당하는 프로퍼티 내용을 조회합니다.

예) curl user-provide1.mgmt.dev.egovp.kr/services

- {"user-provided":[{
  "label": "user-provided",
  "name": "cheolhan",
  "tags": [

  ],
  "instance_name": "cheolhan",
  "binding_name": null,
  "credentials": {
    "id": "admin"
  },
  "syslog_drain_url": "",
  "volume_mounts": [

  ]
},{
  "label": "user-provided",
  "name": "test-provided",
  "tags": [

  ],
  "instance_name": "test-provided",
  "binding_name": null,
  "credentials": {
    "test": "123123123"
  },
  "syslog_drain_url": "",
  "volume_mounts": [

  ]
}]}

curl {URL}/service : (get) 바인드한 서비스들의 목록을 조회합니다.

예) curl user-provide1.mgmt.dev.egovp.kr/service

 - [{"label":"user-provided","name":"cheolhan","tags":[],"instance_name":"cheolhan","binding_name":null,"credentials":               {"id":"admin"},"syslog_drain_url":"","volume_mounts":[]},{"label":"user-provided","name":"test-provided","tags":[],"instance_name":"test-provided","binding_name":null,"credentials":{"test":"123123123"},"syslog_drain_url":"","volume_mounts":[]}


curl {URL}/service/{service_instance_name} : (get) 바인드한 서비스 인스턴스를 조회합니다.

예)curl user-provide1.mgmt.dev.egovp.kr/service/test-provided

- {"label":"user-provided","name":"test-provided","tags":[],"instance_name":"test-provided","binding_name":null,"credentials":{"test":"123123123"},"syslog_drain_url":"","volume_mounts":[]}

끝~
