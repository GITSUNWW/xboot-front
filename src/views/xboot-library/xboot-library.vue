<template>
  <div>
    <Card id="html2canvas">
      <Tabs :animated="false">
        <TabPane label="工具类" id="printjs">
          <Divider orientation="left">打印 - Print.js</Divider>
          <span class="href-text">Github：</span>
          <a
            href="https://github.com/crabbly/Print.js"
            target="_blank"
            class="href-text"
          >https://github.com/crabbly/Print.js</a>
          <br>
          <span class="href-text">官方文档：</span>
          <a
            class="href-text"
            href="http://printjs.crabbly.com"
            target="_blank"
          >http://printjs.crabbly.com</a>
          <br>

          <Button @click="printHtml" class="example-btn">打印网页示例</Button>
          <Button @click="printJson" class="example-btn">打印Json数据示例</Button>

          <Divider orientation="left">截屏 - html2canvas</Divider>
          <span class="href-text">Github：</span>
          <a
            href="https://github.com/niklasvh/html2canvas"
            target="_blank"
            class="href-text"
          >https://github.com/niklasvh/html2canvas</a>
          <br>
          <span class="href-text">官方文档：</span>
          <a
            class="href-text"
            href="https://html2canvas.hertzen.com"
            target="_blank"
          >https://html2canvas.hertzen.com</a>
          <br>

          <Button @click="html2canvas" class="example-btn">截取网页示例</Button>
          <Button @click="html2canvas2" class="example-btn">截取指定内容示例</Button>

          <Divider orientation="left">打印 + 截屏 实现网页样式不丢失打印</Divider>
          <Button @click="html2canvas3" class="example-btn">打印原样式网页图片示例</Button>

          <Divider orientation="left">复制命令 - vue-clipboard2</Divider>
          <span class="href-text">Github：</span>
          <a
            href="https://github.com/Inndy/vue-clipboard2"
            target="_blank"
            class="href-text"
          >https://github.com/Inndy/vue-clipboard2</a>
          <br>
          <span class="href-text">官方文档：</span>
          <a
            class="href-text"
            href="https://github.com/Inndy/vue-clipboard2"
            target="_blank"
          >https://github.com/Inndy/vue-clipboard2</a>
          <br>
          <Button
            v-clipboard:copy="content"
            v-clipboard:success="onCopy"
            v-clipboard:error="onError"
            class="example-btn"
          >复制文本示例</Button>
          <Input
            type="textarea"
            :autosize="{minRows: 2,maxRows: 5}"
            style="width:300px"
            placeholder="粘贴测试"
          />

          <Divider orientation="left">轻量级时间转换工具 - date-fns</Divider>
          <span class="href-text">Github：</span>
          <a
            href="https://github.com/date-fns/date-fns"
            target="_blank"
            class="href-text"
          >https://github.com/date-fns/date-fns</a>
          <br>
          <span class="href-text">官方文档：</span>
          <a class="href-text" href="https://date-fns.org" target="_blank">https://date-fns.org</a>
          <br>

          <span class="href-text">示例：{{time}}</span>
        </TabPane>

        <TabPane label="组件类">
          <Divider orientation="left">省市县级联组件 - iView Area</Divider>
          <span class="href-text">Github：</span>
          <a
            href="https://github.com/iview/iview-area"
            target="_blank"
            class="href-text"
          >https://github.com/iview/iview-area</a>
          <br>
          <span class="href-text">官方文档：</span>
          <a
            class="href-text"
            href="https://iview.github.io/iview-area"
            target="_blank"
          >https://iview.github.io/iview-area</a>
          <br>

          <al-selector v-model="resArr" class="example-btn" style="width: 800px"/>
          {{resArr}}
          <al-cascader v-model="resArr2" class="example-btn" style="width: 400px"/>
          {{resArr2}}
          <Divider orientation="left">树表格 - tree-table-vue</Divider>
          <span class="href-text">Github：</span>
          <a
            href="https://github.com/lison16/tree-table-vue"
            target="_blank"
            class="href-text"
          >https://github.com/lison16/tree-table-vue</a>
          <br>
          <br>

          <div class="operation">
            <Button icon="md-add">添加一级节点</Button>
            <Button icon="md-refresh">刷新</Button>
          </div>
          <Alert show-icon>
            已选择
            <span class="select-count">{{selectCount}}</span> 项
            这里还可以做一些数据统计显示
          </Alert>
          <tree-table
            ref="treeTable"
            index-text="#"
            :data="tableData"
            :columns="columns"
            :stripe="props.stripe"
            :border="props.border"
            :show-header="props.showHeader"
            :show-summary="props.showSummary"
            :show-row-hover="props.showRowHover"
            :show-index="props.showIndex"
            :tree-type="props.treeType"
            :is-fold="props.isFold"
            :expand-type="props.expandType"
            expand-key="name"
            select-type="checkbox"
            @radio-click="handleRadioClick"
            :selectable="props.selectable"
          >
            <template slot="$expand" slot-scope="scope">
              {{ `我的姓名是 ${scope.row.name},
              这一行的索引是 ${scope.rowIndex}.`
              }}
            </template>
            <template slot="action" slot-scope="scope">
              <Button
                type="primary"
                @click="click(scope.row)"
                size="small"
                icon="md-add"
                style="margin-right:5px"
              >添加子节点</Button>
              <Button
                size="small"
                @click="click(scope.row)"
                icon="ios-create-outline"
                style="margin-right:5px"
              >编辑</Button>
              <Button type="error" @click="click(scope.row)" size="small" icon="md-trash">删除</Button>
            </template>
          </tree-table>

          <Divider orientation="left">弹幕视频播放器 - DPlayer</Divider>
          <span class="href-text">Github：</span>
          <a
            href="https://github.com/MoePlayer/DPlayer"
            target="_blank"
            class="href-text"
          >https://github.com/MoePlayer/DPlayer</a>
          <br>
          <span class="href-text">官方文档：</span>
          <a class="href-text" href="http://dplayer.js.org" target="_blank">http://dplayer.js.org</a><br>
          <span class="href-text">自己搭建弹幕服务：</span>
          <a class="href-text" href="https://github.com/MoePlayer/DPlayer-node" target="_blank">https://github.com/MoePlayer/DPlayer-node</a>
          <br>
          <br>

          <div id="dplayer" style="width:600px;height:400px"></div>
        </TabPane>
      </Tabs>
    </Card>

    <Modal title="截屏预览" v-model="modalVisible" :width="1000">
      <img id="render" :src="imgUrl" width="100%" height="500px">
      <div slot="footer">
        <Button type="primary" @click="printPic" v-if="showPrintImage">打印图片</Button>
        <Button @click="modalVisible=false">关闭</Button>
      </div>
    </Modal>
  </div>
</template>

<script>
import printJS from "print-js";
import html2canvas from "html2canvas";
import { format } from "date-fns";
import "dplayer/dist/DPlayer.min.css";
import DPlayer from "dplayer";
export default {
  name: "xboot-library",
  components: {},
  data() {
    return {
      resArr: [],
      resArr2: [],
      modalVisible: false,
      imgUrl: "",
      showPrintImage: false,
      content: "测试文本内容",
      time: "",
      data: [
        {
          id: "1",
          name: "X-BOOT",
          createTime: "2018-08-08 00:08:00",
          updateTime: "2018-08-08 00:08:00"
        },
        {
          id: "2",
          name: "Exrick",
          createTime: "2018-08-08 00:08:00",
          updateTime: "2018-08-08 00:08:00"
        }
      ],
      selectCount: 0,
      props: {
        stripe: false,
        border: true,
        showHeader: true,
        showSummary: false,
        showRowHover: true,
        showIndex: true,
        treeType: true,
        isFold: true,
        expandType: true,
        selectable: true
      },
      ids: "",
      tableData: [
        {
          id: 1,
          name: "Jack",
          sex: "男",
          createTime: "2018-08-08 00:08:00",
          updateTime: "2018-08-08 00:08:00",
          children: [
            {
              id: 2,
              name: "Ashley",
              sex: "女",
              createTime: "2018-08-08 00:08:00",
              updateTime: "2018-08-08 00:08:00",
              children: [
                {
                  id: 3,
                  name: "Ashley",
                  sex: "女",
                  createTime: "2018-08-08 00:08:00",
                  updateTime: "2018-08-08 00:08:00"
                },
                {
                  id: 4,
                  name: "Taki",
                  sex: "男",
                  createTime: "2018-08-08 00:08:00",
                  updateTime: "2018-08-08 00:08:00"
                }
              ]
            },
            {
              id: 5,
              name: "Taki",
              sex: "男",
              createTime: "2018-08-08 00:08:00",
              updateTime: "2018-08-08 00:08:00"
            }
          ]
        },
        {
          id: 6,
          name: "Tom",
          sex: "男",
          createTime: "2018-08-08 00:08:00",
          updateTime: "2018-08-08 00:08:00",
          children: [
            {
              id: 7,
              name: "Ashley",
              sex: "女",
              createTime: "2018-08-08 00:08:00",
              updateTime: "2018-08-08 00:08:00"
            }
          ]
        },
        {
          id: 8,
          name: "Tom",
          sex: "男",
          createTime: "2018-08-08 00:08:00",
          updateTime: "2018-08-08 00:08:00"
        },
        {
          id: 9,
          name: "Tom",
          sex: "男",
          createTime: "2018-08-08 00:08:00",
          updateTime: "2018-08-08 00:08:00",
          children: [
            {
              id: 10,
              name: "Ashley",
              sex: "女",
              createTime: "2018-08-08 00:08:00",
              updateTime: "2018-08-08 00:08:00"
            }
          ]
        }
      ],
      columns: [
        {
          title: "姓名",
          key: "name",
          minWidth: "200px"
        },
        {
          title: "性别",
          key: "sex",
          headerAlign: "center",
          align: "center",
          minWidth: "50px"
        },
        {
          title: "创建时间",
          key: "createTime",
          headerAlign: "center",
          align: "center",
          minWidth: "200px"
        },
        {
          title: "更新时间",
          key: "updateTime",
          headerAlign: "center",
          align: "center",
          minWidth: "200px"
        },
        {
          title: "操作",
          key: "action",
          headerAlign: "center",
          align: "center",
          width: "250px",
          type: "template",
          template: "action"
        }
      ]
    };
  },
  methods: {
    init() {
      this.time = format(new Date(), "YYYY-MM-DD");
      this.initVideo();
    },
    printHtml() {
      printJS("printjs", "html");
    },
    printJson() {
      printJS({
        printable: this.data,
        header: "用户数据",
        gridStyle: "border: 1px solid lightgray;text-align:center",
        properties: ["id", "name", "createTime", "updateTime"],
        type: "json"
      });
    },
    html2canvas() {
      let that = this;
      html2canvas(document.body).then(function(canvas) {
        that.imgUrl = canvas.toDataURL("image/jpeg");
      });
      this.modalVisible = true;
      this.showPrintImage = false;
    },
    html2canvas2() {
      let that = this;
      html2canvas(document.getElementById("html2canvas")).then(function(
        canvas
      ) {
        that.imgUrl = canvas.toDataURL("image/jpeg");
      });
      this.modalVisible = true;
      this.showPrintImage = false;
    },
    html2canvas3() {
      let that = this;
      html2canvas(document.body).then(function(canvas) {
        that.imgUrl = canvas.toDataURL("image/jpeg");
      });
      this.modalVisible = true;
      this.showPrintImage = true;
    },
    printPic() {
      printJS({
        printable: "render",
        type: "html",
        header: "图片数据"
      });
    },
    onCopy() {
      this.$Message.success("复制成功");
    },
    onError() {
      this.$Message.warning("复制失败，请手动复制");
    },
    handleRadioClick(v) {
      this.selectCount = this.$refs.treeTable.getCheckedProp().length;
    },
    click(v) {
      this.$Message.info("点击数据ID为：" + v.id);
    },
    initVideo(v) {
      const dp = new DPlayer({
        container: document.getElementById("dplayer"),
        screenshot: true,
        video: {
          url:
            "https://cloud.video.taobao.com//play/u/95292294/p/1/e/6/t/1/210877258798.mp4"
        },
        danmaku: {
          id: "弹幕ID210877258798",
          api: "https://api.prprpr.me/dplayer/"
        }
      });
    }
  },
  mounted() {
    this.init();
  }
};
</script>

<style lang="less">
.href-text {
  font-size: 12px;
}
.example-btn {
  margin: 10px 0;
  display: block;
}
.operation {
  margin-bottom: 2vh;
}
.select-count {
  font-size: 13px;
  font-weight: 600;
  color: #40a9ff;
}
</style>