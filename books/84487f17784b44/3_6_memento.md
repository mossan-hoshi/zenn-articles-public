---
title: "3_6_Mementoパターン"
---

# 「失われた記憶を取り戻すためのタイムカプセルを発見する友達の物語」

![](/images/20230327_gof/A_group_of_friends_surrounded_by_a_warm_glow_gather_arou.png)
*温かい光に包まれた友人たちが、開いたタイムカプセルを囲み、喜びと懐かしさに満ちた表情で、共通の過去から大切な思い出の品々を手にしています。*

## タイムカプセルの発見

ある絵のように美しい小さな町で、大人になった幼なじみたちが、何年も前に埋めたまま忘れていたタイムカプセルを再発見するために再会を果たしました。彼らの望みは、共有する過去のエッセンスを捉えた思い出の品を取り戻すことでした。

```python
# オブジェクトの状態を保存するMementoクラス
class Memento:
    def __init__(self, state):
        self._state = state

    def get_state(self):
        return self._state
```
## 思い出を掘り起こす

カプセルの正確な位置はわからりませんでしたが、目印になるものをいくつか覚えていました。探しながら、彼らはさまざまな物や手がかりに出くわし、幼い頃の冒険の思い出がよみがえりました。

```python
# メメントオブジェクトの作成と復元を担当するオリジネータークラス
class TimeCapsule:
    def __init__(self, state):
        self._state = state

    def create_memento(self):
        return Memento(self._state)

    def restore_memento(self, memento):
        self._state = memento.get_state()
```
## ジャーニー・スルー・タイム

思い出の品を見つけるたびに、友人たちはまるでタイムスリップしたかのような感覚に陥りました。手紙や絵、小物など、思い出の品々を見つけるたびに、さまざまな感情や過去のエピソードが溢れ出てきました。思い出の品が発掘されるにつれ、彼らは一体感を感じ、自分たちの絆に感謝するようになりました。

```python
Copy code
# メメントスを管理する「ケアテーカー」クラス
class MemoryKeeper:
    def __init__(self):
        self._mementos = []

    def add_memento(self, memento):
        self._mementos.append(memento)

    def get_memento(self, index):
        return self._mementos[index]
```
## 思い出の品に込められた力

ようやく見つけたタイムカプセルを丁寧に開けると、中には大切な思い出の品が入っていました。友人たちはそれぞれ順番に記念品を提示し、それにまつわる思い出を回想し、過去を保存するための記念品のパターンの力を感じていました。

```python
Copy code
# クライアントコード
def main():
    memory_keeper = MemoryKeeper()
    time_capsule = TimeCapsule("Childhood memories")

    memory_keeper.add_memento(time_capsule.create_memento())
    time_capsule._state = "Present time"

    saved_memory = memory_keeper.get_memento(0)
    time_capsule.restore_memento(saved_memory)
    print(time_capsule._state)  # Output: Childhood memories

main()
```
## 絆が深まる

その日が終わると、友人たちはタイムカプセルの本当の価値と思い出に気づきました。タイムカプセルは、自分たちの人生の一部を保存・復元するものであり、その結果、二人の距離を縮めることになりました。思い出を共有し、追体験することで、彼らは絆を大切にし、これからもずっとつながって思い出を作っていこうと誓ったのです。