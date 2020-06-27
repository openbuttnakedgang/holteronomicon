# Пример

Пример СО:  

```json
{
    "@protocol_version": "1.0",
    "@visibility": "public",
    "@control": ["ctrl, io"],
    "@com1": "Это файл описания протокола и только! А не самого устройства c его форматами и функциональностью!",
    "@com2": "Стандартный @access = RO, Если у поля нет вложенных значений, значит указан его тип",
    "@com3": "[sign][path_sz][payload_sz][op][ty][path...][payload...]",
    "@com4": " header max len = 256, payload max len = 256, msg max len = 512",
    "@com5": " max path len = 256 - 5, max payload data len = 256 ",

    "ctrl": {
        "@access": "RW",
        "record" : "bool",
        "vis": "bool",
        "event": { 
            "@type": "[u8]",
            "@access": "WO"
        },
        "erase": "()",
        "goto_loader": "()"
    },

    "io": {
        "@access": "RW",
        "status": "u32",
        "file": {
            "@com": "pos, len, max в блоках",
            "pos": "u32",
            "len": "u32",
            "start": "()",
            "max": {
                "@type": "u32",
                "@access": "RO"
            }
        },
        "store": {
            "@com": "Max line size 64, max line count 64",
            "idx": "u8",
            "line": "[u8]",
            "max": {
                "@type": "u32",
                "@access": "RO"
            }
        }
    },

    "conf": {
        "@access": "RW",
        "cyclic": "bool",
        "time": "u32"
    },

    "time": "u32",

    "signal": {
        "@access": "RW",
        "ecgf": {
            "frq" :"u8"
        },
        "reof": {
            "frq" :"u8"
        },
        "tst_sig": "bool"
    },

    "calib": {
        "@access": "RW",
        "ecg": {
            "k": "i32",
            "b": "i32"
        },
        "reo": {
            "k": "i32",
            "b": "i32"
        },
        "acc": {
            "k": "i32",
            "b": "i32"
        }
    },

    "state": {
        "voltage": "i32",
        "current": "i32",
        "stop_reason": "u32"
    },

    "desc": {             
        "@com": "Общая инфорация об устройстве",
        "version": {
            "@type": "str",
            "@com": "Версия ПО"
        },
        "type": "str",
        "serial": "str"
    },

    "build": {        
        "@access":  "RO",
        "@fast": true,
        "version":  "str",
        "compiler": "str",
        "git":      "str",
        "timestamp":"str",
        "target":   "str",
        "host":     "str",
        "profile":  "str",
        "opt_lvl":  "str",
        "debug":    "bool"
    },

    "dbg": {
        "last": "str",
        "last_code": "u32",
        "flags": "u32"
    },

    "survey": {
        "@access": "RW",
        "id": "u32",
        "surname": "str",
        "name": "str",
        "patronymic": "str",
        "sex": "str",
        "birth": "str",
        "patient_id": "str",
        "start_time": "u32"
    },

    "test": {            
        "@access": "RW",
        "@com": "Тестовые регистры",
        "echo" : {
            "@type": "[u8]",
            "@com": "Эхо тест"
        },
        "test1": "[u8]",
        "test2": "[u8]",
        "test3": "[u8]",
        "test4": "[u8]",
        "test5": "[u8]",
        "error": "str"
    }
}
```