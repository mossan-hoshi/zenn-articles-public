---
title: "3.2 Commandパターン"
---

# 「時間を操る時計を使って歴史を守るタイムトラベラーの物語」

![](/images/20230327_gof/A_time_traveler_stands_beside_an_ancient_clock_its_hands.jpg)
*タイムトラベラーが古時計のそばに立ち、その針が時を超えて渦を巻きながら、歴史的な出来事の渦を巻き起こします。*

## タイムトラベラーと時計

時間が流動的な世界で、勇敢なタイムトラベラー、アレックスは、歴史を操作しようとする者たちから歴史を守るために旅に出ます。神秘的な時計の助けを借りて、アレックスは時間を操作するコマンドを発行することができ、柔軟性と制御を確保するためにコマンドパターンの力を使用します。

```python
# コマンドインターフェース
class TimeCommand:
    def execute(self):
        pass

# 具体的なコマンド
class RewindTimeCommand(TimeCommand):
    def __init__(self, clock):
        self.clock = clock

    def execute(self):
        self.clock.rewind_time()

class FastForwardTimeCommand(TimeCommand):
    def __init__(self, clock):
        self.clock = clock

    def execute(self):
        self.clock.fast_forward_time()
```

## 時計とその力

神秘の時計はインボーカーとして、様々な時間コマンドを記憶し実行することができます。これにより、アレックスは複雑な時間操作のタスクを簡単に実行することができました。

```python
# Invoker
class TimeManipulatorClock:
    def __init__(self):
        self.command = None

    def set_command(self, command: TimeCommand):
        self.command = command

    def manipulate_time(self):
        if self.command:
            self.command.execute()

# Receiver
class Clock:
    def rewind_time(self):
        print("時間が巻き戻される...")

    def fast_forward_time(self):
        print("時間が早送りされています...")
```

## 時間を操作して履歴を保存する

アレックスは時を越えて、時間を操作しなければならない様々な状況に遭遇します。ある例では、古代の芸術品の破壊を防ぐために時間を巻き戻す必要がありました。

```python
clock = Clock()
time_manipulator = TimeManipulatorClock()

rewind_time = RewindTimeCommand(clock)
time_manipulator.set_command(rewind_time)
time_manipulator.manipulate_time()
```

別のシナリオでは、アレックスは時間を早送りして、ある出来事の結果を目撃し、それを変更すべきかどうかを判断する必要があります。

```python
fast_forward_time = FastForwardTimeCommand(clock)
time_manipulator.set_command(fast_forward_time)
time_manipulator.manipulate_time()
```

## 歴史を守る

コマンドパターンを利用することで、アレックスは神秘的な時計を使って効率的に時間を操作することができます。このパターンでは、既存のコードを変更することなく、新しい時間操作コマンドを追加することができ、タイムトラベラーは歴史を守るためのクエストを続けることができます。アレックスと彼らの時計の物語は、コマンドパターンのパワーと柔軟性を証明するものとなっていきます。