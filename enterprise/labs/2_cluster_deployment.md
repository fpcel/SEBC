[root@ip-172-31-44-17 ~]# curl -u fpcel:cloudera "http://ec2-54-154-64-92.eu-west-1.compute.amazonaws.com:7180/api/v2/cm/deployment"
```json
{
  "timestamp" : "2017-06-07T12:49:04.637Z",
  "clusters" : [ {
    "name" : "fpcel",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "644874240"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "644874240"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "912680550"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "153"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-47-47.eu-west-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_passwordseb"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-a729a2c8d2a532919445752e08af9bf4",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0c34014cddde03588"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-355898036a6da1d870786a6b911119b7",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-03e9af1be6b15736e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9gc3gbk9rj5acjhywmrai6p8d"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-355898036a6da1d870786a6b911119b7",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-03e9af1be6b15736e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d0ebqstst8t4zxdorbeeoflqn"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "644874240"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-355898036a6da1d870786a6b911119b7",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-03e9af1be6b15736e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4ixqsm5i2gpa0ovv3yzt5b5gn"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-40e2fda10de318cb94728253ac18def7",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-017daa9a6ca938e57"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2i1692nh3xfi40cg6qaposmpm"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-70fc39fb407ae563647568035e7c2d7f",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0180d69d09677c8c6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3717ddr3o8dm2altaslh144o"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-47-47.eu-west-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue_passwordseb"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-355898036a6da1d870786a6b911119b7"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-355898036a6da1d870786a6b911119b7",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-03e9af1be6b15736e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d4xyjmjikw8whqkfoef3mg6hh"
          }, {
            "name" : "secret_key",
            "value" : "GAuwIdtJvhNxfxfjxBDVoFczTprSCM"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-47-47.eu-west-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_passwordseb"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "644874240"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-355898036a6da1d870786a6b911119b7",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-03e9af1be6b15736e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3dz5iyx1vcsn5gqm26wa0w1cn"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/01/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/01/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "5250"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5250"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "w1u7xiIiMvdqXqbj9jcxISR0eUIftU"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-40e2fda10de318cb94728253ac18def7",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-017daa9a6ca938e57"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e6mxw6dc1jgmnd5181c1p1fyd"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-355898036a6da1d870786a6b911119b7",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-03e9af1be6b15736e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "rlfdvxh4eed39jq23k01xu0q"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-a729a2c8d2a532919445752e08af9bf4",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0c34014cddde03588"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2qdts2bnajmllywvw9tyx3haw"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-e369cade1084febd571edf2e7e1e750c",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0c2cf83f1cee8682f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6s4cqtybkgf6e0j8rz976j47o"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-40e2fda10de318cb94728253ac18def7",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-017daa9a6ca938e57"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "42"
          }, {
            "name" : "role_jceks_password",
            "value" : "eqjrv7whgfsb8ak8y72vocrhf"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/data/01/dfs/dn"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/data/01/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "yoHGTkMxbeRqJxx2DRc0polKMveLWJ"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "WCuuEK8faLfNOJg3dPZApi7aNN0tXm"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "pqb4eqZsEInGUhiREvfGIxvpkRA0Ox"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-40e2fda10de318cb94728253ac18def7",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-017daa9a6ca938e57"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-355898036a6da1d870786a6b911119b7",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-03e9af1be6b15736e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2mebs7vl7bukiny6xupsspzz8"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-a729a2c8d2a532919445752e08af9bf4",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0c34014cddde03588"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "arliu8mkuyxmasvo42obmjoft"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-e369cade1084febd571edf2e7e1e750c",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0c2cf83f1cee8682f"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "851l3illf9rx7oxedcvie874x"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-40e2fda10de318cb94728253ac18def7",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-017daa9a6ca938e57"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4ibvm5mf5rbbdw1ee3bsi3ck5"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-70fc39fb407ae563647568035e7c2d7f",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0180d69d09677c8c6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "rs80huf31boekqoa9kiauid"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-355898036a6da1d870786a6b911119b7",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-03e9af1be6b15736e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3dg1wzwz1k3e80a383udszxpk"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-355898036a6da1d870786a6b911119b7",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-03e9af1be6b15736e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ez283zbmcpe5dstngfon6trse"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-40e2fda10de318cb94728253ac18def7",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-017daa9a6ca938e57"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4nfkwpxse3msv5vhrneiarxcj"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-70fc39fb407ae563647568035e7c2d7f",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0180d69d09677c8c6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9zd0oe20pvp5g9mgfzwu3o8wc"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-40e2fda10de318cb94728253ac18def7",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-017daa9a6ca938e57"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "44"
          }, {
            "name" : "role_jceks_password",
            "value" : "d1q1r4k8ndc4hsgzm8cbqwmbe"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-70fc39fb407ae563647568035e7c2d7f",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0180d69d09677c8c6"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "56"
          }, {
            "name" : "role_jceks_password",
            "value" : "7kwgudq417m99yc90kupyrmv9"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-017daa9a6ca938e57",
    "ipAddress" : "172.31.34.16",
    "hostname" : "ip-172-31-34-16.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0180d69d09677c8c6",
    "ipAddress" : "172.31.39.177",
    "hostname" : "ip-172-31-39-177.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0c2cf83f1cee8682f",
    "ipAddress" : "172.31.40.66",
    "hostname" : "ip-172-31-40-66.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-03e9af1be6b15736e",
    "ipAddress" : "172.31.44.17",
    "hostname" : "ip-172-31-44-17.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0c34014cddde03588",
    "ipAddress" : "172.31.47.47",
    "hostname" : "ip-172-31-47-47.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__6380e078-2b3f-48ee-844c-0c49865be201",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "52b2d4873b36eadd32d97c838babe07205491f7695d11015568e6b2b7926594a",
    "pwSalt" : -5277016072669592941,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-355898036a6da1d870786a6b911119b7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "13bf94814bf48d24bbec8179511c94ab69cf21701d0ccec861d7e6e6fd57a90d",
    "pwSalt" : 8529205229193814411,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-355898036a6da1d870786a6b911119b7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "1d5b847b82a3f4b4be2546161532addb7b80a6da95dee75b7f33fa3bdcb9840d",
    "pwSalt" : 4533252366176356013,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-355898036a6da1d870786a6b911119b7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "7a8ebcde254a409338d58b2193dff3088f4392b91649f5c33d135d0ebada2f50",
    "pwSalt" : 4824860420015492387,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-355898036a6da1d870786a6b911119b7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "be113666bac89850c563a19c3a9eefd49c43e33f775e4ca1e8559b21ae9361e3",
    "pwSalt" : -5728800764241990513,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "cd05cdef469ebc594ed084cf90d95061eecad733575fcc1b0a80dbce7f34dcc7",
    "pwSalt" : 7399242044871161692,
    "pwLogin" : true
  }, {
    "name" : "fpcel",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "cbe96dc2931e7ea590c46989d80e6265b16d46b27e5415bc4edbdf3870c875c4",
    "pwSalt" : -4329409602561463087,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "a689f2fdd736b9a2823036dbde8000a8d050071171f6f3252683827287c1cc7d",
    "pwSalt" : -2531596795537082819,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1014",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "644874240"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "644874240"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "837812224"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-47-47.eu-west-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_passwordseb"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "644874240"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "644874240"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "837812224"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-355898036a6da1d870786a6b911119b7",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-03e9af1be6b15736e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "djpiywcjvc9anyqw80zfhd7sc"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-355898036a6da1d870786a6b911119b7",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-03e9af1be6b15736e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9iuhewf1mq4810ymvisi523ax"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-355898036a6da1d870786a6b911119b7",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-03e9af1be6b15736e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "58j90dfk2uiq410iraqy9s88f"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-355898036a6da1d870786a6b911119b7",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-03e9af1be6b15736e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bvcshxco768mo87yayevywui3"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-355898036a6da1d870786a6b911119b7",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-03e9af1be6b15736e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9nk2dwgqgleajmtpa5elhlmmm"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/24/2012 11:50"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/5.8.3/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```