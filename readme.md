# 产生原因
由于cmake和vscode配合，配置C++开发环境较为负复杂，所以这里直接搭建了一套开发环境，供后续使用
# 部署方法
自用，会用vscode和cmake的自己看得出咋用的
# 部分配置
`tasks.json`:
```json
{
    "options": {
        "cwd": "${workspaceFolder}/build"
    },
    "tasks": [
        {
            "label": "cmake",
            "command": "cmake",
            "args": [
                "-DCMAKE_BUILD_TYPE=Debug",
                ".."
            ]
        },
        {
            "label": "make",
            "command": "make"
        },
        {
            "label": "CMake Build",
            "dependsOn": [
                "cmake",
                "make"
            ]
        }
    ],
    "version": "2.0.0"
}
```